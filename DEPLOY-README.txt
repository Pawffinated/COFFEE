DEPLOYMENT — Pawffinated
==================================================

1. SUPABASE (once)
   SQL Editor → New query → paste all of setup.sql → Run.
   Expect: "Success. No rows returned."
   setup.sql does NOT go into the GitHub repo.

2. GITHUB REPO — upload everything except setup.sql
   and this readme, keeping the folders:

     index.html            (repo root — the POS)
     manifest.json         (repo root — makes it installable)
     icon-192.png          (repo root — home-screen icon)
     icon-512.png          (repo root — splash / store icon)
     version.json          (repo root — in-app updater)
     dashboard/index.html  (owner dashboard)
     selftest/index.html   (deployment self-test — delete after sign-off)

   Then add sw.js WITHOUT uploading a file:
     Add file → Create new file → name it sw.js → paste the
     contents copied from the deployer → Commit changes.
     Without sw.js the POS cannot be reopened offline.

3. GITHUB PAGES
   Settings → Pages → Branch: main, folder: / (root) → Save.
   Allow 1–2 minutes for the first build.

URLS
  POS:       https://Pawffinated.github.io/COFFEE/
  Dashboard: https://Pawffinated.github.io/COFFEE/dashboard/
  Self-test: https://Pawffinated.github.io/COFFEE/selftest/

SIGN-IN
  Owner email:    pawffinated08@gmail.com
  Admin password: Sansanqiqi123*
  Business ID:    77fa344f-8ec9-47a4-b048-c3145e27a9f9

SHOP QR (new in 7.8.0)
  The QR shown for QR / InstaPay payments is embedded inside index.html,
  so it works with the internet down. To change it, edit this line near
  the top of index.html:

    var QR_PAYMENT_IMAGE_URL='data:image/png;base64,...';

  A hosted image URL works too, but it will not display offline.
  Leaving it as an empty string is safe: the sale still records as QR
  and still stays out of the expected cash drawer.

Template version 7.8.0
