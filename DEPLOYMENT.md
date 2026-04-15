# Deployment Guide for Vercel 🚀

Follow these steps to deploy the **Taxi Booking Platform** to Vercel.

## 1. Project Setup on Vercel
1. Log in to [Vercel](https://vercel.com).
2. Click **Add New** > **Project**.
3. Import your Git repository.
4. **IMPORTANT**: In the "Configure Project" step:
   - **Framework Preset**: Select **Next.js**.
   - **Root Directory**: Select **`TaxiServer`**. (Since your app is inside the `TaxiServer` folder).

## 2. Environment Variables
You must add the following environment variables in the Vercel Dashboard (**Settings > Environment Variables**):

| Key | Value (from your .env.local) |
|---|---|
| `NEXT_PUBLIC_SUPABASE_URL` | Your Supabase Project URL |
| `NEXT_PUBLIC_SUPABASE_PUBLISHABLE_DEFAULT_KEY` | Your Supabase Anon Key |
| `NEXT_PUBLIC_OWNER_PHONE` | Your WhatsApp Phone Number (e.g., 919876543210) |

## 3. Build Settings
- **Build Command**: `npm run build`
- **Output Directory**: `.next` (Vercel handles this automatically for Next.js)

> [!NOTE]
> Currently, `next.config.ts` has `output: "export"` enabled. This means Vercel will build the app as a **Static Site**. 
> - If you want to use **Server Side Rendering (SSR)** or **API Routes** later, you should remove `output: "export"` from `next.config.ts`.
> - If you keep it, ensure Vercel sees the `out` directory if it doesn't auto-detect the Next.js build.

## 4. Deploying
Once the variables are set and the root directory is selected, click **Deploy**. Vercel will build and provide you with a production URL! 🎊
