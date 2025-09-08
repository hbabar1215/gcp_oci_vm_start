# AHI 504 — Cloud Foundations for Health Informatics  
## Lab: Launch → Stop → Terminate a VM on **GCP** and **Oracle Cloud (OCI)**

**Purpose.** Practice the full lifecycle of a tiny virtual machine (VM) on two cloud providers. You will (1) create the smallest free/low-cost VM on **GCP** and **OCI**, (2) start/stop it, (3) terminate it, and (4) reflect on similarities/differences in a short screen-recorded video.

**What you’ll gain.** Hands-on familiarity with core IaaS concepts (projects/compartments, regions, shapes/machine types, networking, public IP, boot disks) and cost hygiene (no idle resources).

---

## Outcomes of this assignment: 
1. Create, start, stop, and terminate a minimal VM on GCP and OCI.  
2. Identify key similarities/differences in web console workflows, terminology, and defaults.  
3. Communicate steps clearly in a Markdown tutorial with screenshots.  

---

## Requirements and guardrails
- **Accounts:** Instructor-provisioned access to **Google Cloud** and **Oracle Cloud**.  
- **Regions/Zones:** Choose any available region where tiny/free shapes are offered to you.  
- **Instance size:** Use a **free-tier eligible or the smallest available** general-purpose shape.  
  - *Examples (names vary by account/region):*  
    - GCP: **e2-micro** (or smallest available)  
    - OCI: **VM.Standard.E2.1.Micro** or **VM.Standard.A1.Flex** with minimal OCPU/RAM  
- **OS image:** Ubuntu LTS (or provider default minimal Linux).  
- **No PHI/PII.** Do not store any sensitive data on these VMs.  
- **Security:** If you generate SSH keys, keep private keys private. Do not commit keys to Git.  
- **Cost hygiene:** Stop/terminate all resources when done. Confirm no VMs, disks, or IPs remain.

---

## Deliverables (submit both)
1. **Screen recording (Loom or Zoom, 5–8 minutes).**  
   - Show the full lifecycle on **both** platforms (create → start → stop → terminate).  
   - Narrate:  
     1) **Similarities** in the workflows/terms  
     2) **Differences** (naming, defaults, quotas, UX)  
     3) **Your preference** (OCI vs GCP for a tiny VM) and **why** (clarity, speed, quotas, cost, UI, docs)  
   - Show the resource list **after** termination to confirm cleanup.

2. **Markdown tutorial (`README.md`).**  
   - A concise, step-by-step guide that another student could follow to repeat your process.  
   - Include at least **3 screenshots per platform** (create form, running instance, terminated/cleaned up).  
   - Use headings, bullet steps, and brief notes on pitfalls.

---

## Step-by-step tasks

### Part A — Google Cloud (GCP)
1. **Create/select a project.** Open the console → ensure billing is enabled for this projec (performed in class).  
2. **Choose region/zone.** Pick any available zone (e.g., `us-east1-b`).  
3. **Create VM.** Compute Engine → **Create instance**:  
   - **Machine type:** smallest/free-tier-eligible if available  
   - **Image:** Ubuntu LTS (default minimal)  
   - **Boot disk:** default smallest size  
   - **Network:** default VPC; allow SSH if prompted  
   - **Public IP:** ephemeral  
4. **Start & verify.** Create → wait for **RUNNING**. (Optional: open **Browser SSH**.)  
5. **Stop.** Use **Stop** from the instance actions menu; verify state is **TERMINATED/STOPPED**.  
6. **Delete (terminate).** Use **Delete**; confirm removal.  
7. **Cleanup check.** Verify no leftover **disks**, **snapshots**, or **static IPs**.

### Part B — Oracle Cloud (OCI)
1. **Compartment.** Use the default or create a dedicated *Lab* compartment.  
2. **Create compute instance.** Compute → **Instances** → **Create instance**:  
   - **Shape:** smallest/free-tier-eligible (e.g., `VM.Standard.E2.1.Micro` or minimal `A1.Flex`)  
   - **Image:** Ubuntu (or Oracle Linux if Ubuntu unavailable)  
   - **Boot volume:** default minimal size  
   - **Networking:** attach to your VCN/subnet; assign public IP if required  
   - **SSH keys:** upload a public key if you plan to connect (optional)  
3. **Start & verify.** Launch → wait for state **RUNNING**.  
4. **Stop.** Use **Stop**; verify **STOPPED**.  
5. **Terminate.** Use **Terminate** with **Delete the boot volume** checked.  
6. **Cleanup check.** Confirm no **instances**, **boot volumes**, or **public IPs** remain.

---

## Submission format
- **GitHub (preferred) or LMS upload:**  
  - `README.md` (your tutorial with screenshots embedded)  
  - Link to your **Loom/Zoom** recording at the top of the README  
- **File naming:** `lastname_firstname_vm-lifecycle_gcp-oci.md` if submitting as a single file  
- **Screenshots:** Redact any account IDs or personal info

---

## README.md template (copy/paste)

