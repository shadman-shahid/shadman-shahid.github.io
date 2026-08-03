---
layout: page
title: Personalized-Promo Dashboard
short-title: Personalized-Promo Dashboard
description: Dashboard for auto promo generation based on next-month purchase and lapse prediction from retail data.
img: assets/img/project/pers_promo_n.jpg
importance: 2
category: work
---

A dashboard for __auto promo generation__, built around next-month purchase and lapse prediction from retail data. Periodic (monthly) retail-invoice data extraction was automated with a __cron job__ script and database procedures, feeding a modeling pipeline that used __LSTM__ and __XGBoost__ to predict each customer's likelihood of purchasing next month and their risk of lapsing. These predictions were then used to automatically generate personalized promotional offers targeted at individual customers.

<div style="text-align: center;">
    <img src='/assets/img/project/pers_promo_n.jpg' alt="Personalized-Promo Dashboard" style="width: 80%;" />
</div>

