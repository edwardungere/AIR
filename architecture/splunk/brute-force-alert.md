## DET0551 (Password Guessing via Multi-Source Authentication Failure Correlation)

## Brute force Email Alert

### Query: 

`index="main" source="/var/log/auth.log" dest_user=* "Accept" OR "Accepted" NOT rhost=10.0.*`

### What this does
Searches the main index, and filters by logs originating from auth.log. Further filters by looking for any logs containing any destionation users that were successfully logged into from a remote source not within tehe 10.0.0.0/16 network.

<img width="810" height="693" alt="image" src="https://github.com/user-attachments/assets/79ecf872-4980-44e1-8975-5bb3d9857369" />

## Result email:

<img width="708" height="544" alt="image" src="https://github.com/user-attachments/assets/16b26914-a8b8-477e-9721-e888d0ef88c3" />

