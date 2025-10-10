### Steps to Open a MoMo Merchant Account for Payment Integration

To integrate MoMo as a payment gateway into your business (e.g., for e-commerce, apps, or in-store payments), you need to register as a merchant via MoMo for Business (M4B), their dedicated portal. This process verifies your company and provides API credentials for integration. MoMo is Vietnam's leading e-wallet, licensed by the State Bank of Vietnam, and supports seamless payments via wallet balances, linked banks, cards, and more.

The process is straightforward and can be completed online. It's primarily in Vietnamese, but English support is available via email or hotline. Here's a step-by-step guide based on official documentation:

#### 1. **Prepare Your Business Information**
   Before starting, gather the following requirements (for Vietnamese-registered businesses; foreign entities may need additional localization or partnerships):
   - **Legal Documents**: Business registration certificate (Giấy chứng nhận đăng ký kinh doanh), tax code (Mã số thuế), and company seal (if applicable).
   - **Contact Details**: Valid Vietnamese phone number (for verification), business email, and address.
   - **Bank Account**: A corporate bank account in Vietnam for settlements (must be linked post-registration).
   - **Technical Prep**: Ensure your development team is ready for API integration (docs available post-signup).
   
   Note: Approval typically takes 3–7 business days, depending on document completeness. Minimum transaction volume or revenue thresholds may apply for certain features like Pay Later.

#### 2. **Sign Up on the M4B Portal**
   - Visit the official MoMo for Business portal: [https://business.momo.vn](https://business.momo.vn).
   - Click the **"Sign Up"** (Đăng ký) button on the homepage.
   - Fill out the registration form in three main sections:
     - **Account Information**: Username, password, phone number, and email.
     - **Legal & Business Information**: Company name, tax ID, address, representative details, and business type (e.g., e-commerce, retail).
     - **Other Documents**: Upload scanned copies of your legal docs (PDF/JPG format, under 5MB each).
   - Agree to the terms and submit. You'll receive a verification OTP via SMS/email.

#### 3. **Account Verification**
   - MoMo's team will review your submission (usually within 1–3 days).
   - If additional info is needed, they'll contact you via email or phone.
   - Once approved, you'll get access to the M4B dashboard for managing your account, dashboards, marketing tools, and finance reports.
   - Download the user guide for detailed navigation: [M4B Merchant User Guide (English)](https://business.momo.vn/assets/docs/guide/merchant/User_guide_M4B_merchant(EN).pdf).

#### 4. **Access Test Credentials and Start Integration**
   - Immediately after signup approval, you'll receive **test environment credentials** (Partner Code, Access Key, Secret Key, Public Key) via the dashboard.
   - Head to the MoMo Developers portal: [https://developers.momo.vn/v3/](https://developers.momo.vn/v3/).
     - Explore integration guides for options like Payment Gateway (AIO for multiple channels), QR Code, or Pay Later.
     - Use the test keys to integrate via one simple API (supports SDKs for web, iOS, Android).
     - Minimum API timeout: 30 seconds for reliability.
   - Test your integration in the sandbox environment (no real transactions).

#### 5. **Complete Technical Integration and Go Live**
   - After successful testing, submit your integration for review via the M4B portal (include code samples or demo links).
   - MoMo verifies the technical setup (e.g., secure endpoints, signature handling with RSA).
   - Once approved (1–3 days), request **production keys** from the dashboard.
   - Activate production mode—your merchant account is now live for real payments.
   - Configure settlement (e.g., daily/weekly payouts to your bank) and refunds in the M4B settings.

#### Additional Tips
- **Costs**: No setup or integration fees mentioned; transaction fees are typically 1–2% (confirm during signup).
- **Support**: 
  - Hotline: 1900 636 652 (press 2 for English).
  - Email: merchant.care@momo.vn.
  - Developer support: Via the portal's ticket system.
- **Common Issues**: Ensure your website/app complies with PCI DSS for security. For international merchants, partner with local entities or gateways like Adyen/Nuvei for easier onboarding.
- **Resources**:
  - Full Onboarding Guide: [Merchant Profile Docs](https://developers.momo.vn/v3/docs/payment/onboarding/merchant-profile/).
  - API Reference: [Integration Procedures](https://developers.momo.vn/v3/docs/payment/onboarding/integration-process/).

If you're a foreigner or non-Vietnamese business, contact support first for eligibility. This process empowers your business to tap into MoMo's 30M+ users for higher conversions in Vietnam. If you need code samples for integration, let me know!
