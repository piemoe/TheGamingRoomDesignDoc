# TheGamingRoomDesignDoc
A design doc for a project to develop a game room for a server-based art game

The concept for this design is a "room" for groups of users to play a guessing game with provided images. The "game" will pull a high quality image from a library, progressively render it in more detail for the players, and points are awarded based on who guesses correctly and fastest.

Having explicitly stated goals and plans in the software design will help keep any team together and committed to a similar goal. If the design doc were less directly worded, it could lead to misunderstandings later in development, potentially leading to wasted effort on pieces that won't be needed and rediscussing and refocusing the design doc.

This design doc is a detailed list of considerations for the development team to have when working on this project. Given the cross-platform and server-centered design choices made, this document should give any developer a good point of reference for their choices during their own processes.

One part that wasn't clear in the initial drafts of the document is the exact nature of the game being developed. At early stages, it wasn't clear if the game would be pulling from an image library or allowing users to draw the image themselves. If the latter were the case, everything would need to be handled differently as you'd need constant communication to sync your device's "view" of the drawer's drawing instead of just downloading an image that'll go through the same re-rendering process as everyone else.

In the version moving forward, a single high quality image which is stored on the server will be downloaded by the client. The image will be displayed initially in a low quality form and re-rendered with increasingly higher quality as users are given the chance to guess. As users could be on mobile devices, priority is given to storage conservation; it would be unreasonable for each user to have a copy of everything in the library, so they only download images as needed and freeing the space when it is no longer needed. This could lead to increased bandwidth over time, but will save on initial download load.

For this design, a lot of the load is beared by the server. Rooms are hosted in the server, scores are first synced with the server and updated to users, images are hosted on the server database. This is to minimize load on the user to maximize potential cross-platform experience since users could be on older mobile phones or personal computers.
