Class B subnetting divides a Class B IP address range into smaller sub-networks. Class B IP addresses are typically used for medium-sized networks and have a default subnet mask of **255.255.0.0**, which uses 16 bits for the network portion and 16 bits for the host portion.

### Characteristics of Class B:
- **Default subnet mask**: 255.255.0.0
- **CIDR notation**: /16
- **Total number of IP addresses**: 65,536 (65,534 usable IP addresses after excluding network and broadcast addresses)
- **Range**: 128.0.0.0 to 191.255.255.255

### Subnetting a Class B Network

When subnetting a Class B network, we borrow bits from the host portion (the last two octets) to create more subnets. Since the network portion of a Class B address is already fixed at 16 bits, subnetting focuses on borrowing bits from the host portion.

Let's add an example for subnetting a Class B network into **2 subnets**.

### Example: Subnetting a Class B Network for 2 Subnets

We’ll use the Class B network **172.16.0.0/16** and divide it into **2 subnets**.

#### Steps:

1. **Determine the number of bits to borrow**:  
   To create 2 subnets, we calculate:
   \[
   2^n \geq 2 \Rightarrow 2^1 = 2
   \]
   We need to borrow **1 bit** from the host portion.

2. **New subnet mask**:  
   The default subnet mask for Class B is **255.255.0.0 (/16)**.  
   By borrowing 1 bit, we add this to the network portion, resulting in a new subnet mask of **/17**.  
   In decimal, the new subnet mask becomes **255.255.128.0**.

3. **Subnet increment**:  
   Since we have borrowed 1 bit, 15 bits remain for the host portion. The subnet increment is:
   \[
   2^{15} = 32,768 \text{ IP addresses per subnet}
   \]
   This gives each subnet **32,766 usable IP addresses** (excluding the network and broadcast addresses).

4. **Subnets**:  
   With 1 bit borrowed, we create 2 subnets. Here are the subnets:

   - **Subnet 1**: 172.16.0.0/17  
     Range: 172.16.0.1 to 172.16.127.254  
     Network address: 172.16.0.0  
     Broadcast address: 172.16.127.255

   - **Subnet 2**: 172.16.128.0/17  
     Range: 172.16.128.1 to 172.16.255.254  
     Network address: 172.16.128.0  
     Broadcast address: 172.16.255.255

### Summary:

- **/17** gives you 2 subnets, each with **32,766 usable IP addresses**.

By borrowing just one bit, the address space is divided into two large subnets, each capable of handling a significant number of hosts.

Class A subnetting follows the same principles as Class B and Class C subnetting but operates on a larger IP address range. The default subnet mask for Class A is **255.0.0.0**, meaning the first 8 bits are reserved for the network portion, and the remaining 24 bits are used for the host portion.

### Characteristics of Class A:
- **Default subnet mask**: 255.0.0.0
- **CIDR notation**: /8
- **Total number of IP addresses**: 16,777,216 (16,777,214 usable IP addresses after excluding network and broadcast addresses)
- **Range**: 1.0.0.0 to 126.255.255.255

### Subnetting a Class A Network

When subnetting a Class A network, we borrow bits from the host portion (the last three octets) to create subnets. Since the network portion of a Class A address is already fixed at 8 bits, subnetting focuses on borrowing bits from the host portion.

### Example 1: Subnetting a Class A Network for 2 Subnets

We’ll use the Class A network **10.0.0.0/8** and divide it into **2 subnets**.

#### Steps:

1. **Determine the number of bits to borrow**:  
   We need 2 subnets, so:
   \[
   2^n \geq 2 \Rightarrow 2^1 = 2
   \]
   We need to borrow **1 bit** from the host portion.

2. **New subnet mask**:  
   The default subnet mask for Class A is **255.0.0.0 (/8)**.  
   By borrowing 1 bit, we extend the network portion, resulting in a new subnet mask of **/9**.  
   The new subnet mask in decimal is **255.128.0.0**.

3. **Subnet increment**:  
   Since we borrowed 1 bit, 23 bits remain for the host portion. The subnet increment is:
   \[
   2^{23} = 8,388,608 \text{ IP addresses per subnet}
   \]
   Each subnet will have **8,388,606 usable IP addresses** (excluding the network and broadcast addresses).

4. **Subnets**:

   - **Subnet 1**: 10.0.0.0/9  
     Range: 10.0.0.1 to 10.127.255.254  
     Network address: 10.0.0.0  
     Broadcast address: 10.127.255.255

   - **Subnet 2**: 10.128.0.0/9  
     Range: 10.128.0.1 to 10.255.255.254  
     Network address: 10.128.0.0  
     Broadcast address: 10.255.255.255

### Example 2: Subnetting a Class A Network for 4 Subnets

We’ll use the same Class A network **10.0.0.0/8** and divide it into **4 subnets**.

#### Steps:

1. **Determine the number of bits to borrow**:  
   We need 4 subnets, so:
   \[
   2^n \geq 4 \Rightarrow 2^2 = 4
   \]
   We need to borrow **2 bits** from the host portion.

2. **New subnet mask**:  
   By borrowing 2 bits, we add these to the network portion, resulting in a new subnet mask of **/10**.  
   The new subnet mask in decimal is **255.192.0.0**.

3. **Subnet increment**:  
   Since we borrowed 2 bits, 22 bits remain for the host portion. The subnet increment is:
   \[
   2^{22} = 4,194,304 \text{ IP addresses per subnet}
   \]
   Each subnet will have **4,194,302 usable IP addresses** (excluding the network and broadcast addresses).

4. **Subnets**:

   - **Subnet 1**: 10.0.0.0/10  
     Range: 10.0.0.1 to 10.63.255.254  
     Network address: 10.0.0.0  
     Broadcast address: 10.63.255.255

   - **Subnet 2**: 10.64.0.0/10  
     Range: 10.64.0.1 to 10.127.255.254  
     Network address: 10.64.0.0  
     Broadcast address: 10.127.255.255

   - **Subnet 3**: 10.128.0.0/10  
     Range: 10.128.0.1 to 10.191.255.254  
     Network address: 10.128.0.0  
     Broadcast address: 10.191.255.255

   - **Subnet 4**: 10.192.0.0/10  
     Range: 10.192.0.1 to 10.255.255.254  
     Network address: 10.192.0.0  
     Broadcast address: 10.255.255.255

### Summary:

- **/9**: 2 subnets, each with **8,388,606 usable IP addresses**.
- **/10**: 4 subnets, each with **4,194,302 usable IP addresses**.



### Example 1: Subnetting a Class B Network for 4 Subnets

Let's take the Class B network **172.16.0.0/16** and divide it into **4 subnets**.

1. **Determine the number of bits to borrow**:  
   We need to create 4 subnets, so we calculate:
   \[
   2^n \geq \text{{Number of required subnets}} \Rightarrow 2^2 = 4
   \]
   So, we need to borrow 2 bits.

2. **New subnet mask**:  
   The default subnet mask for Class B is **255.255.0.0 (/16)**.  
   By borrowing 2 bits, we add these to the network portion, resulting in a **/18** subnet mask.  
   The new subnet mask in decimal becomes **255.255.192.0**.

3. **Subnet increment**:  
   Since we borrowed 2 bits, we now have 14 bits for the host portion. The subnet increment is:
   \[
   2^{14} = 16,384 \text{{ IP addresses per subnet}}
   \]
   This gives us 16,382 usable addresses in each subnet (after excluding network and broadcast addresses).

4. **Subnets**:  
   With 2 bits borrowed, we can create 4 subnets. Here are the subnets:

   - **Subnet 1**: 172.16.0.0/18  
     Range: 172.16.0.1 to 172.16.63.254  
     Network address: 172.16.0.0  
     Broadcast address: 172.16.63.255

   - **Subnet 2**: 172.16.64.0/18  
     Range: 172.16.64.1 to 172.16.127.254  
     Network address: 172.16.64.0  
     Broadcast address: 172.16.127.255

   - **Subnet 3**: 172.16.128.0/18  
     Range: 172.16.128.1 to 172.16.191.254  
     Network address: 172.16.128.0  
     Broadcast address: 172.16.191.255

   - **Subnet 4**: 172.16.192.0/18  
     Range: 172.16.192.1 to 172.16.255.254  
     Network address: 172.16.192.0  
     Broadcast address: 172.16.255.255

### Example 2: Subnetting a Class B Network for 8 Subnets

Let’s take **172.16.0.0/16** and subnet it to create **8 subnets**.

1. **Determine the number of bits to borrow**:  
   We need 8 subnets, so:
   \[
   2^n \geq 8 \Rightarrow 2^3 = 8
   \]
   We need to borrow 3 bits from the host portion.

2. **New subnet mask**:  
   By borrowing 3 bits, we extend the network portion by 3 bits, so the new subnet mask is **/19**.  
   In decimal, the new subnet mask is **255.255.224.0**.

3. **Subnet increment**:  
   Since we have borrowed 3 bits, the remaining bits for the host portion are 13. The subnet increment is:
   \[
   2^{13} = 8,192 \text{{ IP addresses per subnet}}
   \]
   This means each subnet will have **8,190 usable IP addresses** (after excluding network and broadcast addresses).

4. **Subnets**:  
   With 3 bits borrowed, we can create 8 subnets. Here are the subnets:

   - **Subnet 1**: 172.16.0.0/19  
     Range: 172.16.0.1 to 172.16.31.254  
     Network address: 172.16.0.0  
     Broadcast address: 172.16.31.255

   - **Subnet 2**: 172.16.32.0/19  
     Range: 172.16.32.1 to 172.16.63.254  
     Network address: 172.16.32.0  
     Broadcast address: 172.16.63.255

   - **Subnet 3**: 172.16.64.0/19  
     Range: 172.16.64.1 to 172.16.95.254  
     Network address: 172.16.64.0  
     Broadcast address: 172.16.95.255

   - **Subnet 4**: 172.16.96.0/19  
     Range: 172.16.96.1 to 172.16.127.254  
     Network address: 172.16.96.0  
     Broadcast address: 172.16.127.255

   - **Subnet 5**: 172.16.128.0/19  
     Range: 172.16.128.1 to 172.16.159.254  
     Network address: 172.16.128.0  
     Broadcast address: 172.16.159.255

   - **Subnet 6**: 172.16.160.0/19  
     Range: 172.16.160.1 to 172.16.191.254  
     Network address: 172.16.160.0  
     Broadcast address: 172.16.191.255

   - **Subnet 7**: 172.16.192.0/19  
     Range: 172.16.192.1 to 172.16.223.254  
     Network address: 172.16.192.0  
     Broadcast address: 172.16.223.255

   - **Subnet 8**: 172.16.224.0/19  
     Range: 172.16.224.1 to 172.16.255.254  
     Network address: 172.16.224.0  
     Broadcast address: 172.16.255.255

### Example 3: Subnetting a Class B Network for 16 Subnets

Let’s subnet **172.16.0.0/16** to create **16 subnets**.

1. **Determine the number of bits to borrow**:  
   We need 16 subnets, so:
   \[
   2^n \geq 16 \Rightarrow 2^4 = 16
   \]
   We need to borrow 4 bits.

2. **New subnet mask**:  
   By borrowing 4 bits, we extend the network portion to **/20**.  
   In decimal, the new subnet mask is **255.255.240.0**.

3. **Subnet increment**:  
   With 4 bits borrowed, 12 bits remain for the host portion. The subnet increment is:
   \[
   2^{12} = 4,096 \text{{ IP addresses per subnet}}
   \]
   So each subnet will have **4,094 usable IP addresses**.

4. **Subnets**:  
   With 4 bits borrowed, we can create 16 subnets:

   - **Subnet 1**: 172.16.0.0/20  
     Range: 172.16.0.1 to 172.16.15.254  
     Network address: 172.16.0.0  
     Broadcast address: 172.16.15.255

   - **Subnet 2**: 172.16.16.0/20  
     Range: 172.16.16.1 to 172.16.31.254  
     Network address: 172.16.16.0  
     Broadcast address: 172.16.31.255

   - **Subnet 3**: 172.16.32.0/20  
     Range: 172.16.32.1 to 172.16.47.254  
     Network address: 172.16.32.0  
     Broadcast address: 172.16.47.255

   - **Subnet 4**: 172.16.48.0/20  
     Range: 172.16.48.1 to 172.16.63.

254  
     Network address: 172.16.48.0  
     Broadcast address: 172.16.63.255

   - **Subnet 5**: 172.16.64.0/20  
     Range: 172.16.64.1 to 172.16.79.254  
     Network address: 172.16.64.0  
     Broadcast address: 172.16.79.255

   - **Subnet 6**: 172.16.80.0/20  
     Range: 172.16.80.1 to 172.16.95.254  
     Network address: 172.16.80.0  
     Broadcast address: 172.16.95.255

   - **Subnet 7**: 172.16.96.0/20  
     Range: 172.16.96.1 to 172.16.111.254  
     Network address: 172.16.96.0  
     Broadcast address: 172.16.111.255

   - **Subnet 8**: 172.16.112.0/20  
     Range: 172.16.112.1 to 172.16.127.254  
     Network address: 172.16.112.0  
     Broadcast address: 172.16.127.255

   - **Subnet 9**: 172.16.128.0/20  
     Range: 172.16.128.1 to 172.16.143.254  
     Network address: 172.16.128.0  
     Broadcast address: 172.16.143.255

   - **Subnet 10**: 172.16.144.0/20  
     Range: 172.16.144.1 to 172.16.159.254  
     Network address: 172.16.144.0  
     Broadcast address: 172.16.159.255

   - **Subnet 11**: 172.16.160.0/20  
     Range: 172.16.160.1 to 172.16.175.254  
     Network address: 172.16.160.0  
     Broadcast address: 172.16.175.255

   - **Subnet 12**: 172.16.176.0/20  
     Range: 172.16.176.1 to 172.16.191.254  
     Network address: 172.16.176.0  
     Broadcast address: 172.16.191.255

   - **Subnet 13**: 172.16.192.0/20  
     Range: 172.16.192.1 to 172.16.207.254  
     Network address: 172.16.192.0  
     Broadcast address: 172.16.207.255

   - **Subnet 14**: 172.16.208.0/20  
     Range: 172.16.208.1 to 172.16.223.254  
     Network address: 172.16.208.0  
     Broadcast address: 172.16.223.255

   - **Subnet 15**: 172.16.224.0/20  
     Range: 172.16.224.1 to 172.16.239.254  
     Network address: 172.16.224.0  
     Broadcast address: 172.16.239.255

   - **Subnet 16**: 172.16.240.0/20  
     Range: 172.16.240.1 to 172.16.255.254  
     Network address: 172.16.240.0  
     Broadcast address: 172.16.255.255

### Summary:

- **/18**: 4 subnets, each with **16,382 usable IP addresses**.
- **/19**: 8 subnets, each with **8,190 usable IP addresses**.
- **/20**: 16 subnets, each with **4,094 usable IP addresses**.

Let me know if you'd like further clarification!
