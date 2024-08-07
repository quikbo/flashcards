# Flash Cards Web Application

This is a simple flash cards web application that allows users to create, edit, and delete flash cards and decks.

## Run locally

1. Clone this repository.

2. Navigate to the project directory.

3. To run the server API:

   1. Navigate to the `api` directory.
   2. Install the dependencies by running `pnpm install`.
   3. Create the database with `pnpm db:push`.
   4. Seed the database with `pnpm db:seed`.
   5. Run the server with `pnpm dev`. This will start the server on `http://localhost:3000`.

4. To run the application:

   1. Navigate to the `web` directory.
   2. Add a `.env` file to `web` directory with the following content:

        ```bash
        VITE_API_URL=http://localhost:3000
        ```

   3. Install the dependencies by running `pnpm install`.
   4. Run the application with `pnpm run dev`. This will start the application on `http://localhost:5173`.


   TODOS:

   API
  - update seed to make names decks and cards

   - account for UNIQUE constraint when registering accounts DONE
   - disconnect cards from users DONE
   - add validate session route to auth DONE
   - make sure the 4 auth routes have proper responses DONE
   - every decks and cards route is forbidden if not signed in DONE
      - users can only see their own decks, therfore they can only do CRUD stuff on their own stuff DONE
      - add forbidden conditionals for all crud routes if user.id !== deck/card user id DONE
   

   WEB
   -make layout more even looking DONE
   - routes that look good on web: fetching decks, adding decks, editing decks, deleting decks, fetching cards, editing cards, adding cards, deleting cards DONE
   -redirect users to login page automatically when accessing site if no session detected DONE


   -if signed in, make going to login or register page redirect to home page DONE
   -cant open register page  DONE 
   -update header when there are 0 decks or cards to look nice DONE

   -try being signed in, deleting session or db studio, and make sure that trying
      to interact w web app sends u to login page; 
      - stale user information in local storage, use validate session for this DONE

   -trying to access forbidden objects makes error toasts pop up DONE

