# Nmap

- To avoid getting blocked, we must slow down Nmap scan.

  ```
  nmap -F -T1 <target> -v
  ```

  - `-F`: Tells Nmap to scan only the most common 100 ports, which is useful for quickly identifying open services on a target without spending too much time.
  - `-T1`: Represents the timing template. `T1` is the slowest template.
  - `-v`: Enables verbose mode to provide detailed information during the scan.

# ffuf

- Used for web fuzzing.

  ```
  ffuf -w <path-to-wordlist> -u <target> -p 1
  ```

  - `-w <path-to-wordlist>`: Specify the path to the wordlist you want to use.
  - `-u <target>`: Provide the target URL you want to fuzz.
  - `-p 1`: Set the concurrency level to 1 for sending one request at a time.

- good wordlist for varios ffuf scans [GitHub - SecLists](https://github.com/danielmiessler/SecLists.git).

# shodan

- scans network automatically and stores it it's database
- useful tool to use when we are not allowed to scan the target
- for example lets assume wordpress 1.4.7 had a new cve and was vulnerable. Below is how we can identify all servers that are running wordpress 1.4.7

  ```
  shodan download <wordpressfile.txt> "wordpress 1.4.7"
  ```

  - `-download`: The subcommand for downloading data from Shodan's database
  - `-wordpressfile.txt`: The name you're giving to the downloaded file.
  - `-wordpress 1.4.7`: The search query or filter to find data related to WordPress version 1.4.7.

- we can get info onspecific ips `shodan host <ip>`

# note taking

- cherrytree is good free program to take notes
- note node hierarchy domain > subdomain > software > recon
