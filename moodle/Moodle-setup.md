## How moodle was sat up:

1. Set up a Bitnami image with AWS, single-tier, picking a small T2. Costs amount to ~20$ a month.
2. Added an A-record to the main domain(copenhagencoaching.dk) for the moodle EC2 IP(edu.copenhagencoaching.dk).
3. Configured an SSL with the IP of EC2 and the new domain we created to redirect from http to https, using “bncert-tool”, which is built in the moodle image on EC2.
sudo `/opt/bitnami/bncert-tool`

Renewing of the certificate:
1. Get private key from @carolineolivia
2. Where the private key is placed run:
`ssh -i "PRIVATE_KEY" bitnami@edu.copenhagencoaching.dk`
3. Run `/opt/bitnami/bncert-tool`
4. Run `edu.copenhagencoaching.dk`on the list
5. When asking for email, use prolike@copenhagencoaching.dk

[Docs about `/opt/bitnami/bncert-tool`](https://docs.bitnami.com/virtual-machine/faq/administration/generate-configure-certificate-letsencrypt/)
