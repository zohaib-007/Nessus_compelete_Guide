# Complete Guide to Installing and Using Nessus on Kali Linux
Nessus is a world-class vulnerability assessment tool used by security professionals to scan networks, detect misconfigurations,
find unpatched systems, and identify vulnerabilities before exploits happen.

## Step 1: Download the Nessus Package

Nessus is a proprietary tool, meaning it cannot be installed directly via apt install. You must download the official Debian package.
  * Head over to the official Tenable Nessus Downloads page.
  * Download the latest Linux installation package for Debian/Kali (usually ends with -debian10_amd64.deb or similar).
  * Alternatively, move the package to your machine or download it via the terminal (replace the URL with the latest version link if needed)

                                             wget https://tenable.com
<p align="center">
  <img src="https://example.com">
</p>


## Step 2: Install Nessus via Terminal
Once the .deb file is downloaded, use the Debian Package Manager (dpkg) to complete the installation.

  * Navigate to your downloads directory
    
                                                 cd ~/Downloads

<p align="center">
  <img src="https://example.com">
</p>

  * Run the installation package using sudo privileges

                                  sudo dpkg -i Nessus-10.8.3-debian10_amd64.deb



## Step 3: Start and Enable the Nessus Service

Nessus runs as a web-based local daemon. After installation, the service is stopped by default.

   * Start the Nessus system service daemon

                                          sudo systemctl start nessusd


   * Enable the service to launch automatically every time you power on Kali Linux
    
                                         sudo systemctl enable nessusd
    
   * Verify that the service is running actively
     
                                         sudo systemctl status nessusd
<p align="center">
  <img src="https://example.com">
</p>


## Step 4: Access the Web interface & Activation

Nessus utilizes a local web server interface listening on Port 8834 over SSL (https).
    * Open your Kali Linux web browser and navigate to
    
                                          https://localhost:8834/

**Note:** You might encounter an SSL certificate warning screen. Click Advanced and then click Accept the Risk and Continue).

1. Choose Nessus Essentials (the free-tier package which permits scanning up to 16 commercial IP addresses).
2. Input your email address to receive your free personal Activation Code.
3. Create your primary Administrator Username and Password to complete the setup wizard.
4. Wait for the program to download and compile its extensive vulnerability Plugins database (this step can take up to 20-30 minutes).

<p align="center">
  <img src="https://example.com">
</p>


## Step 5: Run a Real-Life Vulnerability Scan

Once compilation finishes, you can configure your first target infrastructure evaluation.

  1. Build a New Target Plan

       • Click on New Scan in the upper right-hand corner.
       • Choose the Basic Network Scan configuration blueprint.

<p align="center">
  <img src="https://example.com">
</p>
    

  3. Configure Real-World Scoping

  Fill out the parameters inside the target module:
  
   * **Name:** Internal Home Network Lab
   * **Description:** Vulnerability assessment check on the router and local sandbox machine.
   * **Targets:** Enter your target subnet range or single machine IP (e.g., your local home router at 192.168.1.1 or a sandbox machine at 192.168.1.50).

  3. Launch and Watch Live

   * Click the Save drop-down array option and select Launch to initiate your live analysis packet delivery.
   * Click directly on your running item instance to see real-time updates inside the dashboard.

# Step 6: Analyzing the Real-World Scan Results

When your assessment wraps up, Nessus groups discovered vulnerabilities under color-coded threat bands:

<p align="center">
  <img src="https://example.com">
</p>

* **Critical (Red)**: Severe unpatched vulnerabilities or remote code execution risks (e.g., Log4Shell or EternalBlue). Immediate mitigation required.
* **High (Orange)**: Dangerous configuration oversights, directory traversals, or outdated encryption types.
* **Medium (Yellow):** Minor cryptographic flaws or sensitive cleartext data transmission channels.
* **Low/Info (Green/Blue):** Open system ports, network configuration banners, and target environmental data.

# Step 7: Exporting Your Vulnerability Report

To share findings with network administrators or attach your threat logs to an assessment portfolio:
1. Click into the complete assessment instance page.
2. Click the Report button in the dashboard action panel.
3. Select PDF or HTML report format layouts.
4. Choose the Executive Summary options preset for structured documentation or Custom fields for fine-grained raw data analysis files.


                                                 
