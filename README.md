# NextAuth Session Undefined in getServerSideProps After Login

This repository demonstrates a bug where the NextAuth session is undefined in `getServerSideProps` after a successful login. The issue occurs when navigating from the home page to the about page.

## Bug Description

The about page fetches the session using `getServerSideProps`. After logging in, the session object remains undefined, even though the login is successful. This prevents the about page from accessing the user's session data.

## Setup

1. Clone this repository.
2. Install dependencies: `npm install`
3. Run the development server: `npm run dev`

## Steps to Reproduce

1. Navigate to the home page.
2. Click the "Go to About Page" link.
3. Notice that the about page shows "Not logged in" despite successful authentication. 
4. Check the network tab of your browser's developer tools to ensure the `/api/auth/[...nextauth]` endpoint is called and returning a valid response.  (This checks the authentication process itself).
5. If you refresh the about page, the session should populate. This confirms the issue lies in the serverside prop retrieval on the initial load.