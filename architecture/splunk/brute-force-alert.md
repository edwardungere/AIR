## Brute force Alert

### Query: 

`index="main" source="/var/log/auth.log" dest_user=* "Accept" OR "Accepted" NOT rhost=10.0.*`

### What this does
Searches the main index, and filters by logs originating from auth.log. Further filters by looking for any logs containing any destionation users that were successfully logged into from a remote source not within tehe 10.0.0.0/16 network.

<img width="810" height="693" alt="image" src="https://github.com/user-attachments/assets/79ecf872-4980-44e1-8975-5bb3d9857369" />

## Resulting email:

<img width="708" height="544" alt="image" src="https://github.com/user-attachments/assets/16b26914-a8b8-477e-9721-e888d0ef88c3" />
<br>
<img width="1139" height="264" alt="image" src="https://github.com/user-attachments/assets/43f78908-0542-4874-9e71-8e9bad858004" />

## Reports
<img width="1417" height="312" alt="image" src="https://github.com/user-attachments/assets/4c19d198-0bf2-4140-a3d2-5f1283f08a4f" /> <br>

- Shows the total number of brute force attempts per IP address (Left) <br>
- Shows the failed password attempts for (existing) accounts on the instances (Right) <br>
- Adversaries may use a list of generic password, this report filters out any nonexistent accounts
