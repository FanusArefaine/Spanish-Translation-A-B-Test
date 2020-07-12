# Spanish-Translation-A-B-Test
A project to confirm that the result of A/B test carried out in a company is actually right. 


# Problem Description
Company XYZ is a worldwide e-commerce site with localized versions of the site.

A data scientist at XYZ noticed that Spain-based users have a much higher conversion rate than any other Spanish-speaking country. She therefore went and talked to the international team in charge of Spain And LatAm to see if they had any ideas about why that was happening.

Spain and LatAm country manager suggested that one reason could be translation. All Spanish- speaking countries had the same translation of the site which was written by a Spaniard. They agreed to try a test where each country would have its one translation written by a local.

After they run the test however, they are really surprised cause the test is negative. I.e., it appears that the non-localized translation was doing better!

You are asked to:

    * Confirm that the test is actually negative. That is, it appears that the old version of the site with just one translation across Spain and LatAm performs better

    * Explain why that might be happening. Are the localized translations really worse?


# Data
We have 2 tables:

test_table : general information about the test results

Columns:

    *user_id : the id of the user. Unique by user. Can be joined to user id in the other table. For each user, we just check whether conversion happens the first time they land on the site since the test started.

    *date : when they came to the site for the first time since the test started

    *source : marketing channel: Ads, SEO, Direct .

    *browser_language : in browser or app settings, the language chosen by the user. It can be EN, ES, Other (Other means any language except for English and Spanish)

    *ads_channel : if marketing channel is ads, this is the site where the ad was displayed. It can be: Google, Facebook, Bing, Yahoo ,Other. If the user didn’t come via an ad, this field is NA

    *browser : user browser. It can be: IE, Chrome, Android_App, FireFox, Iphone_App, Safari, Opera

    *conversion : whether the user converted (1) or not (0). This is our label. A test is considered successful if it increases the proportion of users who convert.

    *test : users are randomly split into test (1) and control (0). Test users see the new translation and control the old one. For Spain-based users, this is obviously always 0 since there is no change there.



user_table - Information about the user

Columns:

    *user_id : the id of the user. It can be joined to user id in the other table sex : user sex: Male or Female

    *age : user age (self-reported)

    *country : user country based on ip address