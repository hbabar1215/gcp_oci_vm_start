# VM Lifecycle on GCP and OCI — Tutorial

## Video
Loom/Zoom: [VM Lifecycle Tutorial](https://drive.google.com/file/d/1m4hDOGO8tKH3R-98T-m6qQ832lKdJW5k/view?usp=sharing) 
Zoom: [OCI Clean up](https://drive.google.com/file/d/18b4k8t5noMsza9N9SFDHPnhy7Zvi6GpP/view?usp=sharing)
(I made a small clip to show another way we can double check our clean up in OCI by going into boot volume attachments)
## Prereqs
- Cloud access to GCP and OCI
- No PHI/PII; smallest/free-tier shapes

---

## Google Cloud (GCP)
### Create
1. Console → Compute Engine → Create instance: test-ahi
2. Region/zone: us-central1b
3. Machine type: E2.Micro
4. Image: Ubuntu LTS
5. Boot disk: default minimal
6. Network: default VPC; ephemeral public IP


### Start/Stop
- Start:

![GCP create](assignment_1/gcp/gcpcreate.png)

- Stop:

![GCP stopped](assignment_1/gcp/gcpstop.png)

### Delete
- Delete instance and verify no disks/IPs remain

![GCP cleaned](assignment_1/gcp/gcpclean.png)

---

## Oracle Cloud (OCI)
### Create
1. Compartment: humababar (root)
2. Networking: VCN with Internet Connectivity (defaults)
3. Shape: VM.Standard.A1.Flex
4. Image: Ubuntu
5. Public IP: ephemeral
6. Boot volume: default minimal

### Start/Stop
- Start: <state shows RUNNING>

![OCI create](assignment_1/oci/ocicreate.png)

- Stop: 

![OCI stop](assignment_1/oci/ocistop.png)

### Terminate
- Terminate and delete boot volume; verify cleanup

![OCI terminated](assignment_1/oci/ociterminate.png)

### Verify Cleanup
![OCI cleaned](assignment_1/oci/oci_clean.png)

---

## Reflections
### Similarities
- Both have "create instances" button 
- Choosing an OS image and shape
- Adding SSH key pairs
- Both allow us to create small free tier VMs

### Differences
- The GCP layout is easier to understand/use
- In GCP you choose specific regions/zones
- In OCI there is a drop down bar for start stop and terminate while in GCP each action has a separate button 
- GCP uses machine types (like E2) while OCI uses shapes for their vm
- Terminated vm is visibly present for some time in OCI but immediately gone in GCP.

### Preference (OCI vs GCP) and Why
- Even though OCI looks better graphically, I prefer using GCP because it is more user-friendly and has a better clean up process when terminating a vm. For example, when terminating a vm on OCI it still lives there giving users the chance to review the vm and restore if needed. It hard deletes after a couple of hours while in GCP the terminated vm is deleted right away. Additionally, I like how symbols are used in GCP. When a vm is "running" there is a green check symbol next to the instance name and when the vm is "stopped" there is a gray pause symbol. GCP will also show you how many credits you have left in your billing account for students. 
