<img src=https://github.com/user-attachments/assets/f50ae817-2209-4e7e-9290-30747a17b7ef width=500 height=300 />

Class C subnetting is a process used to divide a Class C IP address range into smaller sub-networks (subnets). Class C IP addresses are typically assigned to smaller networks and are represented by an IP address where the first three octets (24 bits) are reserved for network identification, and the last octet (8 bits) is used for host identification.

### Characteristics of Class C:
- **Default subnet mask**: 255.255.255.0
- **CIDR notation**: /24 (24 bits for the network portion)
- **Total number of IP addresses**: 256 (254 usable IP addresses, excluding network and broadcast addresses)
- **Range**: 192.0.0.0 to 223.255.255.255

### Subnetting a Class C Network

To subnet a Class C network, we "borrow" bits from the host portion of the address (the last octet) to create more networks. Subnetting allows dividing a large network into smaller, more manageable sub-networks.

#### Example:

Let's say we have the IP address **192.168.1.0/24** and we want to create 4 subnets. The default subnet mask for a Class C address is **255.255.255.0**, and now we will borrow some bits from the host portion to create subnets.

### Step-by-step Subnetting

1. **Determine the number of subnets**: 
   If we want 4 subnets, we need to calculate how many bits to borrow from the host portion.

   Formula:  
   \[
   2^n \geq \text{{Number of required subnets}}
   \]
   Where \( n \) is the number of bits borrowed.

   For 4 subnets, we need at least 2 bits:  
   \[
   2^2 = 4 \text{{ subnets}}
   \]

2. **New subnet mask**: 
   We borrow 2 bits from the host portion. The default subnet mask is **255.255.255.0 (/24)**. By borrowing 2 bits, we now have 26 bits for the network portion. So the new subnet mask is **255.255.255.192 (/26)**.

3. **Determine the subnet increment**:
   The subnet increment is determined by the borrowed bits. In this case, 2 bits were borrowed, which means the subnet increment is 64. This increment value comes from the binary place value of the remaining host bits.

4. **Identify the subnets**:
   The network address **192.168.1.0/26** can be divided into 4 subnets, with each subnet having 64 IP addresses (including the network and broadcast addresses).

   Here are the subnets:

   - **Subnet 1**: 192.168.1.0/26  
     Range: 192.168.1.1 to 192.168.1.62  
     Network address: 192.168.1.0  
     Broadcast address: 192.168.1.63

   - **Subnet 2**: 192.168.1.64/26  
     Range: 192.168.1.65 to 192.168.1.126  
     Network address: 192.168.1.64  
     Broadcast address: 192.168.1.127

   - **Subnet 3**: 192.168.1.128/26  
     Range: 192.168.1.129 to 192.168.1.190  
     Network address: 192.168.1.128  
     Broadcast address: 192.168.1.191

   - **Subnet 4**: 192.168.1.192/26  
     Range: 192.168.1.193 to 192.168.1.254  
     Network address: 192.168.1.192  
     Broadcast address: 192.168.1.255

### Summary:
- By borrowing 2 bits, we created 4 subnets.
- Each subnet has 62 usable IP addresses (64 total IP addresses, but 2 are reserved for the network and broadcast addresses).
- Subnet mask: **255.255.255.192** or **/26**.

This allows efficient IP address allocation by dividing a Class C network into smaller sub-networks.

Let's explore more examples of Class C subnetting with different scenarios.

### Example 1: Subnetting for 8 Subnets

We will subnet the network **192.168.10.0/24** to create **8 subnets**.

1. **Determine the number of bits to borrow**:  
   We need 8 subnets, so we calculate:
   \[
   2^n \geq \text{{Number of subnets}} \Rightarrow 2^3 = 8
   \]
   We need to borrow 3 bits.

2. **New subnet mask**:  
   The default subnet mask for Class C is **255.255.255.0 (/24)**.  
   After borrowing 3 bits, the new subnet mask becomes **/27**.  
   In decimal, the new subnet mask is **255.255.255.224**.

3. **Subnet increment**:  
   The subnet increment is determined by the number of bits left for the host portion. With 3 bits borrowed, the remaining host bits are 5. The subnet increment is:
   \[
   2^5 = 32
   \]
   So, the increment between subnets is 32.

4. **Subnets**:  
   The network **192.168.10.0/27** can be divided into 8 subnets, each with 32 IP addresses (30 usable).

   - **Subnet 1**: 192.168.10.0/27  
     Range: 192.168.10.1 to 192.168.10.30  
     Network address: 192.168.10.0  
     Broadcast address: 192.168.10.31

   - **Subnet 2**: 192.168.10.32/27  
     Range: 192.168.10.33 to 192.168.10.62  
     Network address: 192.168.10.32  
     Broadcast address: 192.168.10.63

   - **Subnet 3**: 192.168.10.64/27  
     Range: 192.168.10.65 to 192.168.10.94  
     Network address: 192.168.10.64  
     Broadcast address: 192.168.10.95

   - **Subnet 4**: 192.168.10.96/27  
     Range: 192.168.10.97 to 192.168.10.126  
     Network address: 192.168.10.96  
     Broadcast address: 192.168.10.127

   - **Subnet 5**: 192.168.10.128/27  
     Range: 192.168.10.129 to 192.168.10.158  
     Network address: 192.168.10.128  
     Broadcast address: 192.168.10.159

   - **Subnet 6**: 192.168.10.160/27  
     Range: 192.168.10.161 to 192.168.10.190  
     Network address: 192.168.10.160  
     Broadcast address: 192.168.10.191

   - **Subnet 7**: 192.168.10.192/27  
     Range: 192.168.10.193 to 192.168.10.222  
     Network address: 192.168.10.192  
     Broadcast address: 192.168.10.223

   - **Subnet 8**: 192.168.10.224/27  
     Range: 192.168.10.225 to 192.168.10.254  
     Network address: 192.168.10.224  
     Broadcast address: 192.168.10.255

### Example 2: Subnetting for 16 Subnets

Now, let’s subnet the network **192.168.20.0/24** to create **16 subnets**.

1. **Determine the number of bits to borrow**:  
   We need 16 subnets, so we calculate:
   \[
   2^n \geq 16 \Rightarrow 2^4 = 16
   \]
   We need to borrow 4 bits.

2. **New subnet mask**:  
   The default subnet mask is **255.255.255.0 (/24)**.  
   After borrowing 4 bits, the new subnet mask becomes **/28**.  
   In decimal, the new subnet mask is **255.255.255.240**.

3. **Subnet increment**:  
   The remaining 4 bits are for the host portion, so the subnet increment is:
   \[
   2^4 = 16
   \]
   So, the increment between subnets is 16.

4. **Subnets**:  
   The network **192.168.20.0/28** can be divided into 16 subnets, each with 16 IP addresses (14 usable).

   - **Subnet 1**: 192.168.20.0/28  
     Range: 192.168.20.1 to 192.168.20.14  
     Network address: 192.168.20.0  
     Broadcast address: 192.168.20.15

   - **Subnet 2**: 192.168.20.16/28  
     Range: 192.168.20.17 to 192.168.20.30  
     Network address: 192.168.20.16  
     Broadcast address: 192.168.20.31

   - **Subnet 3**: 192.168.20.32/28  
     Range: 192.168.20.33 to 192.168.20.46  
     Network address: 192.168.20.32  
     Broadcast address: 192.168.20.47

   - **Subnet 4**: 192.168.20.48/28  
     Range: 192.168.20.49 to 192.168.20.62  
     Network address: 192.168.20.48  
     Broadcast address: 192.168.20.63

   - **Subnet 5**: 192.168.20.64/28  
     Range: 192.168.20.65 to 192.168.20.78  
     Network address: 192.168.20.64  
     Broadcast address: 192.168.20.79

   - **Subnet 6**: 192.168.20.80/28  
     Range: 192.168.20.81 to 192.168.20.94  
     Network address: 192.168.20.80  
     Broadcast address: 192.168.20.95

   - **Subnet 7**: 192.168.20.96/28  
     Range: 192.168.20.97 to 192.168.20.110  
     Network address: 192.168.20.96  
     Broadcast address: 192.168.20.111

   - **Subnet 8**: 192.168.20.112/28  
     Range: 192.168.20.113 to 192.168.20.126  
     Network address: 192.168.20.112  
     Broadcast address: 192.168.20.127

   - **Subnet 9**: 192.168.20.128/28  
     Range: 192.168.20.129 to 192.168.20.142  
     Network address: 192.168.20.128  
     Broadcast address: 192.168.20.143

   - **Subnet 10**: 192.168.20.144/28  
     Range: 192.168.20.145 to 192.168.20.158  
     Network address: 192.168.20.144  
     Broadcast address: 192.168.20.159

   - **Subnet 11**: 192.168.20.160/28  
     Range: 192.168.20.161 to 192.168.20.174  
     Network address: 192.168.20.160  
     Broadcast address: 192.168.20.175

   - **Subnet 12**: 192.168.20.176/28  
     Range: 192.168.20.177 to 192.168.20.190  
     Network address: 192.168.20.176  
     Broadcast address: 192.168.20.191

   - **Subnet 13**: 192.168.20.192/28  
     Range: 192.168.20.193 to 192.168.20.206  
     Network address: 192.168.20.192  
     Broadcast address: 192.168.20.207

   - **Subnet 14**: 192.168.20.208/28  
     Range: 192.168.20.209 to 192.168.20.222  
     Network address: 192.168.20.208  
     Broadcast address: 192.168.20.223

   - **Subnet 15**: 192.168.20.224/28  
     Range: 192.168.20.225 to 192.168.20

.238  
     Network address: 192.168.20.224  
     Broadcast address: 192.168.20.239

   - **Subnet 16**: 192.168.20.240/28  
     Range: 192.168.20.241 to 192.168.20.254  
     Network address: 192.168.20.240  
     Broadcast address: 192.168.20.255

### Example 3: Subnetting for 2 Subnets

Let’s take **192.168.30.0/24** and subnet it to create **2 subnets**.

1. **Determine the number of bits to borrow**:  
   We need 2 subnets, so:
   \[
   2^n \geq 2 \Rightarrow 2^1 = 2
   \]
   We borrow 1 bit.

2. **New subnet mask**:  
   Borrowing 1 bit from the host portion, the new subnet mask becomes **/25**.  
   In decimal, the subnet mask is **255.255.255.128**.

3. **Subnet increment**:  
   Since 7 bits remain for the host portion, the increment is:
   \[
   2^7 = 128
   \]
   So, the increment between subnets is 128.

4. **Subnets**:

   - **Subnet 1**: 192.168.30.0/25  
     Range: 192.168.30.1 to 192.168.30.126  
     Network address: 192.168.30.0  
     Broadcast address: 192.168.30.127

   - **Subnet 2**: 192.168.30.128/25  
     Range: 192.168.30.129 to 192.168.30.254  
     Network address: 192.168.30.128  
     Broadcast address: 192.168.30.255

### Summary:

- **/27** gives you **8 subnets**, each with **30 usable IPs**.
- **/28** gives you **16 subnets**, each with **14 usable IPs**.
- **/25** gives you **2 subnets**, each with **126 usable IPs**.

