<h1>Multi Threaded Proxy Server with and without Cache</h1>
##### I implemented multi-threading by opting for semaphores instead of condition variables and the `pthread_join()` and `pthread_exit()` functions. The `pthread_join()` function necessitates the thread ID of the thread to wait for, while semaphore operations like `sem_wait()` and `sem_post()` do not require any parameters, making semaphores a more efficient and straightforward option.

##### The motivation for this project stems from a desire to understand several key aspects of network and server operations. Firstly, we aimed to comprehend how requests travel from our local computer to the server. Additionally, we wanted to explore how to handle multiple client requests from various sources simultaneously, including the locking procedures necessary for concurrency. Understanding the concept of caching and the different functions browsers might use was also a key objective. A proxy server plays a crucial role in speeding up processes and reducing server-side traffic. It can restrict users from accessing specific websites, and an effective proxy can anonymize client requests by changing the IP address. Furthermore, modifications to the proxy can be made to encrypt requests, preventing unauthorized access to client data.
