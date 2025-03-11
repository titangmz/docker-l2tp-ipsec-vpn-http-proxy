# 🌐 HTTP Proxy via IPsec L2TP VPN in Docker  

A Docker image to run an HTTP proxy over an IPsec/L2TP VPN client. Based on [docker-ipsec-vpn-client](https://github.com/emmdim/docker-ipsec-vpn-client).  

## 🚀 Setup Instructions  

### 1️⃣ Clone the Repository  
```bash  
git clone <repo-url>  
cd docker-l2tp-ipsec-vpn-http-proxy  
```  

### 2️⃣ Configure VPN Credentials  
Edit the `docker-compose.yml` file and set the following environment variables:  

| Variable            | Description                                  |  
|---------------------|----------------------------------------------|  
| `VPN_IPSEC_PSK`    | VPN Pre-Shared Key (provided by VPN provider) |  
| `VPN_USER`         | VPN Username                                 |  
| `VPN_PASSWORD`     | VPN Password                                 |  
| `VPN_PUBLIC_IP`    | VPN Server Host/IP                           |  
| `VPN_LOCAL_IP`     | Your local machine’s IP                     |  

### 3️⃣ Start the Container  
Run the following command to launch the proxy:  
```bash  
./dockerstart.sh  
```  

### 4️⃣ Stop the Container  
To terminate the container, run:  
```bash  
./dockerstop.sh  
```  

---  

## 🖥️ Using the HTTP Proxy  
Once the container is running, you can use the HTTP proxy in your applications.  

### Example: Puppeteer  
```javascript  
puppeteer.launch({ args: ['--proxy-server=localhost:8040'] });  
```  

You can now browse with the VPN's IP via the HTTP proxy. 🎉  
