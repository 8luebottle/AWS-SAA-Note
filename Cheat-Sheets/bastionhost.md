# Bastion Host
> A bastion host is a server whose purpose is to provide access to a private network from an external network, such as the Internet.

- Bastion Host == Jump Box

- Minimize the chances of penetration.

- `Deploy`:
  - in the `public subnet`.
  - within each AZ (HA).

- Mitigate the risk of allowing SSH connections from an external network.  

  ![bastion host](https://user-images.githubusercontent.com/48475824/145698993-87a9d178-f075-479a-b259-d43b88a67d0c.png)

  - record all SSH sessions.
