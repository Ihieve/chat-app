# DD CHAT — Your circle, your space

DD CHAT is a mobile-first group chat experience for close friends. It uses a dark purple interface, Supabase authentication, Postgres persistence, and Supabase Realtime.

## Links

- Live preview: https://dd-chat-mu.vercel.app/
- Source code: https://github.com/Ihieve/chat-app

## Stack

- Static HTML, CSS and JavaScript (easy to deploy on Vercel)
- Supabase JS v2
- Supabase Auth, Postgres with Row Level Security (RLS), and Realtime

## Run locally

You can serve `index.html` with any static web server, or open it through a local dev server. The Supabase client is loaded from jsDelivr, so an internet connection is required.

1. Create a Supabase project.
2. Run [supabase/schema.sql](supabase/schema.sql) in the Supabase SQL Editor.
3. Serve `index.html` and open it in your browser.
4. Choose **Connect Supabase** and enter the Project URL plus the browser-safe publishable key (or legacy anon key).
5. Create an account or sign in. Test persistence after refresh, then test real-time messages in a second browser session.

## Security

- Never put a Supabase secret key, `service_role` key, SMTP password, or database password in client-side code or commit one to GitHub.
- The browser publishable/anon key is only safe when RLS policies are correct.
- Room membership must be provisioned by a trusted admin/server-side flow. Do not add a public policy that lets users add themselves to private rooms.
- Review the SQL and test the access policies with two separate accounts before inviting friends.
- The initial UI only activates `The Group Chat`; other sample room buttons remain locked until membership management is implemented.

## Roadmap

- [x] Starter UI and Supabase connection flow
- [x] Authentication and persistent message insert/load
- [x] Initial membership-aware database schema
- [ ] Verify real-time delivery between separate accounts
- [ ] Secure admin-managed invitation links and room membership UI
- [ ] Message reactions, replies, and pins
- [ ] DD Moments shared memory timeline
- [ ] Vibe Check polls and Circle Challenges
- [ ] Secure image and voice-note storage
