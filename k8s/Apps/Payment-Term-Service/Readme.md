create following secrets
1. kafka_username
2. kafka_password

for creating secret use base64 string (copy without %)
echo -n "your string" | openssl enc -base64 -A 