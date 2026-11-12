Part 1
1. Create a cloud instance
2. Connect via ssh (remotely to the server)
    - ssh -i key.pem ubuntu@<PUBLIC_IP>

Part 2
1. To update system packages - sudo apt update && sudo apt upgrade -y
2. Install Docker - sudo apt install docker.io -y
3. Verify docker installation - sudo systemctl status docker
4. Install Nginx web server - sudo apt install nginx -y
5. Start and enable Nginx - sudo systemctl enable --now nginx
6. Verify Nginx is running - 	sudo systemctl status nginx

Part 3
1. Configure AWS networking - Allow inbound TCP port 80
2. Access the Nginx welcome page - http://13.211.146.118/

Part 4
1. Records incoming HTTP requests - sudo tail -n 50 /var/log/nginx/access.log
2. Records errors encountered by nginx - sudo tail -n 50 /var/log/nginx/error.log
3. Displays the latest 50 journal entries associated with the Nginx service. - sudo journalctl -u nginx -n 50 --no-pager

4. First,save access logs - sudo tail -n 50 /var/log/nginx/access.log > ~/nginx-logs.txt
5. Second, append error logs - sudo tail -n 50 /var/log/nginx/error.log >> ~/nginx-logs.txt
6. Third, append systemd logs - sudo journalctl -u nginx -n 50 --no-pager >> ~/nginx-logs.txt
7. verify the saved file - ls -lh ~/nginx-logs.txt

Part 5
Download the log file to the local computer
    scp -i "C:\path\to\your-key.pem" ubuntu@<PUBLIC_IP>:/home/ubuntu/nginx-logs.txt .