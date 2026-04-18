# Funnel-and-Retention-Analysis---MercadoLibre
Context: User behavior on MercadoLibre was analyzed between January and August 2025, using event and activity data to map the conversion funnel and evaluate retention by cohort. The objective was to identify at which stages users are lost and how effective the platform is at retaining them over time.

Analysis: A multi-stage funnel was built in SQL using CTEs, measuring conversion from first visit to purchase and calculating rates between each step (COUNT DISTINCT of users).
The analysis was segmented by country, device, and traffic source to detect variations in behavior.
In parallel, a cohort retention analysis was performed, calculating metrics D7, D14, D21, and D28 from user registration data.
This approach allowed for the identification of drop-off points and the evaluation of engagement quality throughout the user lifecycle.

Conclusions: The greatest drop in the funnel occurs in intermediate stages (typically between add_to_cart and begin_checkout or during the payment process), indicating friction in purchase intent.
There are significant differences by segment: some countries or devices show lower conversion rates, suggesting issues with user experience or local context.
Retention shows a progressive decline after registration, with few active users after days 14–28, demonstrating weakness in repeat purchases. Key insight: The loss of value occurs not only in conversion but also in retention, which directly impacts the user's lifetime value (LTV).
