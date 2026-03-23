# S3 Notes

### Object storage
- Flat system, data is stored as self-contained objects
- Folder paths are strictly naming convention
- Each object is bundled with its own metadata and unique identifier (key)
- No partial updates, if writing to data, object needs to be downloaded, edited, then reuploaded
- Amazon S3

### File storage
-  Traditional hiearcheal system
- Use folders and paths
- Can be shared like a network drive
- Amazon EFS
  
### Block storage
- Raw chuncks of data, no inherent structure
- Fast, low latency, good for databases and OS volumes
- Amazon EBS

### Object ownership
- Bucket owner controls all objects in the bucket, and ACLs are disabled.
- Access is controlled by bucket policy

### Bucket policies (Resource-based permissions)
- Replaced ACLs (legacy option)
- Attached to bucket
- Can be used together with IAM

- If cross-account, both identity-based and resource-based needs allow ✅
- If same account, identity-based or resource-based need allow ✅
- If either has explicit deny ❌
- If no policy, implicit deny ❌

### Identity and Resource-based permissions
<img width="573" height="463" alt="image" src="https://github.com/user-attachments/assets/1c1235f6-c8ca-43f4-9243-1f7b2b06824d" />
