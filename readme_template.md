# VM Lifecycle on GCP and OCI — Tutorial

## Video
Loom/Zoom: [VM Lifecycle Tutorial](assignment_1/video2920590959.mp4)

## Prereqs
- Cloud access to GCP and OCI
- No PHI/PII; smallest/free-tier shapes

---

## Google Cloud (GCP)
### Create
1. Console → Compute Engine → Create instance
2. Region/zone: <us-central1b>
3. Machine type: <E2.Micro>
4. Image: Ubuntu LTS
5. Boot disk: default minimal
6. Network: default VPC; ephemeral public IP


### Start/Stop
- Start:
![GCP create](assignment_1/gcprunning.png)

- Stop:
![GCP stopped](assignment_1/gcpstopped.png)

### Delete
- Delete instance and verify no disks/IPs remain

![GCP cleaned](assignment_1/gcpcleaned.png)

---

## Oracle Cloud (OCI)
### Create
1. Compartment: humababar (root)
2. Networking: VCN with Internet Connectivity (defaults)
3. Shape: VM.Standard.A1.Flex
4. Image: Ubuntu
5. Public IP: ephemeral
6. Boot volume: default minimal

![OCI create](assignment_1/ocirunning.png)

### Start/Stop
- Start: <state shows RUNNING>
![OCI running](assignment_1/ocistopped.png)

- Stop: 
![OCI terminated](assignment_1/ociterminated.png)

### Terminate
- Terminate and delete boot volume; verify cleanup

![OCI cleaned](assignment_1/ociclean.png)

---

## Reflections
### Similarities
- <brief bullets>

### Differences
- <brief bullets>

### Preference (OCI vs GCP) and Why
- <one short paragraph>
