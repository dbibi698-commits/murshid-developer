# Feature and API Guide

- `GET /api/health` — app status
- `GET /api/videos?q=...&kind=short|long&category=...&sort=latest|popular` — feed/search
- `GET /api/channels?q=...` — channel search
- `POST /api/register`, `POST /api/login`, `POST /api/logout` — account
- `POST /api/upload` — authenticated multipart upload
- `GET /api/video/<id>` — play video and record a view
- `PATCH /api/video/<id>` — edit own video metadata (JSON)
- `DELETE /api/video/<id>` — delete own video
- `POST /api/video/<id>/react` — like/dislike (JSON action)
- `POST /api/video/<id>/comment` — add comment
- `POST /api/subscribe/<email>` — toggle subscription
- `GET /api/channel/<email>` — channel details/videos
- `POST /api/profile`, `POST /api/password` — profile/password
- `GET /api/notifications`, `POST /api/notifications/read` — notifications
- `GET /api/history` — signed-in user's watch history
- `/api/admin/*` — admin-only moderation APIs

API endpoints are documented for developers; not every endpoint has a dedicated frontend control yet.

- Shorts three-dot menu: Description with view count, Save to playlist, Ambient mode, captions toggle, fullscreen, playback speed, Not interested, hide channel, report, and feedback.


## Live streaming update
- Mobile-style fixed bottom navigation: Home, Shorts, Create, Live, You, More.
- Agora Web SDK live broadcast supports camera/microphone or screen share, plus a server-backed live room list and polling live chat.
- The supplied Agora App ID is configured in `static/app.js`. For demo use, the Agora project must have token authentication disabled. For production, enable authentication and implement a server-side short-lived RTC token endpoint; never expose an App Certificate in client code.
- Screen capture requires HTTPS or localhost and browser permission.
