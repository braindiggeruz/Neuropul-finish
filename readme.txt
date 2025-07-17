TRAE AWAKENS FLOW - README
==========================

Project: Neuropul AI - Telegram WebApp Flow
Version: 1.0.0
Author: Neuropul AI Core
Date: 2025-01-16

DESCRIPTION
-----------
This flow implements the core logic for Trae Awakens experience in Neuropul AI.
Designed for Telegram WebApp integration with XP system, PDF generation, and user progression.

FLOW LOGIC
----------
1. START → User opens Telegram WebApp
2. INITDATA VALIDATION → Validate Telegram WebApp initData (min 100 chars)
3. API SYNC → Call /api/sync-progress to get user XP and progress
4. XP CHECK → Branch based on user XP level:
   - High XP (≥100): Generate PDF
   - Medium XP (≥50): Award bonus XP
   - Low XP (<50): Show progress message
5. PDF GENERATION → Create personalized awakening report
6. DELIVERY → Send PDF with download link
7. CTA → Portal/Dashboard navigation options
8. COMPLETION → Analytics and flow end

KEY FEATURES
------------
- Strict initData validation for security
- Graceful error handling with fallbacks
- Dynamic XP-based branching
- PDF generation with personalization
- Auto-retry mechanisms for API calls
- Analytics tracking
- Mobile-optimized UI messages

VARIABLES
---------
- initData: Telegram WebApp initialization data
- userId: Extracted Telegram user ID
- userXP: Current user experience points
- questStep: User's quest progression
- pdfUrl: Generated PDF download URL

API ENDPOINTS
-------------
- POST /api/sync-progress: Sync user data and XP
- POST /api/pdf: Generate personalized PDF report

ERROR HANDLING
--------------
- Invalid initData → Error message + retry option
- API failures → Auto-retry with exponential backoff
- Low XP → Motivational message + quest suggestions
- Network issues → Graceful degradation

IMPORT INSTRUCTIONS
-------------------
1. Upload trae-flow.json to Bolt New
2. Configure API endpoints in settings
3. Set up Telegram WebApp integration
4. Test with valid initData
5. Deploy and monitor analytics

SUPPORT
-------
For technical support or customization:
- Documentation: See metadata.json
- Schema: See schema.png
- Contact: Neuropul AI Core Team

NOTES
-----
- Requires Telegram Bot API integration
- PDF generation needs external service
- XP thresholds can be customized
- Flow supports A/B testing variants
- Mobile-first design approach