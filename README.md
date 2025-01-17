<h1>Multi Threaded Proxy Server with and without Cache</h1>

I implemented multi-threading by opting for semaphores instead of condition variables and the `pthread_join()` and `pthread_exit()` functions. The `pthread_join()` function necessitates the thread ID of the thread to wait for, while semaphore operations like `sem_wait()` and `sem_post()` do not require any parameters, making semaphores a more efficient and straightforward option.

The motivation for this project stems from a desire to understand several key aspects of network and server operations. Firstly, we aimed to comprehend how requests travel from our local computer to the server. Additionally, we wanted to explore how to handle multiple client requests from various sources simultaneously, including the locking procedures necessary for concurrency. Understanding the concept of caching and the different functions browsers might use was also a key objective. A proxy server plays a crucial role in speeding up processes and reducing server-side traffic. It can restrict users from accessing specific websites, and an effective proxy can anonymize client requests by changing the IP address. Furthermore, modifications to the proxy can be made to encrypt requests, preventing unauthorized access to client data.

##### OS Component Used ​
The project utilized several key OS components to achieve its functionality. Threading was implemented to manage multiple operations concurrently, while locks were employed to ensure proper synchronization and avoid conflicts. Semaphores were used to control access to shared resources efficiently. Additionally, caching was implemented using the Least Recently Used (LRU) algorithm to optimize performance by storing frequently accessed data and reducing retrieval times.

## How to Run

```bash
$ git clone https://github.com/YashSinghal1512/ProxyServerMulti-Threaded.git
$ cd MultiThreadedProxyServerClient
$ make all
$ ./proxy <port no.>
```

##### Limitations ​
If a URL triggers multiple clients, the cache will store each client's response as a separate element in the linked list. Consequently, when retrieving from the cache, only a portion of the response might be sent, preventing the website from fully opening. Additionally, the cache elements have a fixed size that means large websites may not be stored in the cache.

##### How this project can be extended? ​
The code can be enhanced by implementing multiprocessing, which would speed up the process through parallelism. We can also extend the code to decide which types of websites should be allowed.

# Note:
This code can only be run in Linux Machine. Please disable your browser cache. To run the proxy without cache Change the name of the file (`proxy_server_with_cache.c to proxy_server_without_cache.c`) MakeFile.

