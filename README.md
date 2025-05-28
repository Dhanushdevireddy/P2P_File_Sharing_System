# **BitTorrent Clone**

This project replicates the core functionality of BitTorrent, providing a decentralized file-sharing network where clients can register, join groups, share files, and download from other peers. It is built with a tracker-client model, supporting group management, file sharing, and dynamic ownership handling.

---

## **Instructions to Run the Code**

### 1. **Running the Tracker**

* Navigate to the `tracker` folder:

  ```bash
  cd tracker
  ```
* Execute the `make` command to create the `tracker` executable:

  ```bash
  make
  ```
* Run the tracker with the following command, replacing `tracker_info.txt` and `tracker_no` with your specific tracker info file and tracker number:

  ```bash
  ./tracker tracker_info.txt tracker_no
  ```

### 2. **Running the Client**

* Navigate to the `client` folder:

  ```bash
  cd client
  ```
* Execute the `make` command to create the `client` executable:

  ```bash
  make
  ```
* Run the client with the following command, replacing `Ip:port` with the tracker’s IP address and port, and `tracker_info.txt` with your tracker info file:

  ```bash
  ./client Ip:port tracker_info.txt
  ```

---

## **Features Implemented**

### **User Authentication and Group Management:**

1. **Account Creation & Registration**: Clients can create an account and register with the tracker.
2. **Login**: Clients can log in using their credentials.
3. **Group Creation**: Clients can create new groups, where they are the default owner.
4. **Group Ownership Transfer**: If the group owner leaves, the first member who joined the group becomes the new owner.
5. **Group Listing**: Clients can fetch and view all available groups in the network.
6. **Join/Leave Groups**: Clients can request to join any group and leave a group at any time.
7. **Group Access Control**: Only the owner of the group can list or accept join requests to the group.

### **File Sharing and Downloading:**

8. **File Sharing**: Clients can upload details of files they have (filename, SHA1 hash) to the group.
9. **Fetch Shared Files**: After joining a group, clients can fetch a list of all sharable files in that group.
10. **File Downloading**: Clients can download files shared within a group, provided the seeder (peer with the file) is online.
11. **Seeding Control**: Seeders can stop sharing files whenever they choose.
12. **Automatic File Sharing on Login**: When a client logs back in, all previously shared files are automatically set to sharing mode again.
13. **Download Progress**: Clients can view ongoing and completed downloads.
14. **File Transfer Privacy**: Once logged out, none of the client's files will be shared.

---

## **Technologies Used**

* **C++**: For client-server interactions, file management, and networking.
* **Makefile**: For building the tracker and client applications.
* **SHA1**: For file integrity verification and uniqueness.
