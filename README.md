# Islamic Inheritance & Wasiyyah Calculator

A single-file, production-ready, client-side web application designed to compute primary Islamic estate distribution rules (*Ilm al-Fara'id*). It seamlessly integrates financial liabilities, voluntary bequests, and core Quranic heir distributions according to standard Sunni jurisprudence (Hanafi, Maliki, Shafi'i, and Hanbali).

---

## 🌟 Features

*   **Strict Financial Precedence Hierarchy:** Deducts funeral expenses and outstanding liabilities from the gross estate pool *before* processing legacy distributions or fixed fractional shares.
*   **The 1/3 Bequest Safeguard (*Wasiyyah* & *Sadakah*):** Combines voluntary wills and ongoing charities (*Sadakah Jariyah*), automatically enforcing the strict Shariah legal ceiling of **$1/3$ ($33.33\%$)** of the remaining net estate. It applies a proportional cap and issues an alert if the user exceeds this maximum limit.
*   **Dynamic UI Adjustments:** Real-time adaptation based on the deceased's gender, dynamically handling options such as multi-wife fraction pooling or spouse-based criteria omission.
*   **Core Shariah Principles Automated:**
    *   **Spousal Shifts:** Adjusts husband ($1/2 \rightarrow 1/4$) or wife ($1/4 \rightarrow 1/8$) configurations depending on the existence of children.
    *   **Residuary Allocation (*Asabah*):** Distributes the remainder to children following the divine **2:1 ratio** (sons receive double the share of daughters).
    *   **Over-allocation Protection (*Awl*):** Automatically detects and triggers a mathematical scale-down if the primary Quranic fixed fractions exceed $1.0$.

---

## 🛠️ Installation & Usage

Since this is a fully self-contained application, it requires no external frameworks, dependencies, servers, or API keys.

1.  **Save the Code:** Copy the provided source code and save it as an HTML file, for example: `calculator.html`.
2.  **Run Locally:** Double-click the file to open it instantly in any modern web browser (Chrome, Firefox, Safari, Edge).
3.  **Embed in CMS (WordPress/Webflow):** Copy the inner content of the `<style>` block into your global CSS customizer, and paste the HTML structure and `<script>` logic directly into a Custom HTML block.

---

## 📐 Mathematical Order of Execution

The calculator processes user input using the exact sequence prescribed in Islamic jurisprudence:

$$\text{Gross Estate} \xrightarrow{-\text{Debts/Funeral}} \text{Net Estate} \xrightarrow{-\text{Bequests (Max 1/3)}} \text{Net Faraid Pool} \rightarrow \text{Fixed Heirs} \rightarrow \text{Residuary Heirs}$$

1.  **Net Estate Assessment:** 
    $$\text{Net Estate} = \text{Total Estate} - \text{Funeral \& Debts}$$
2.  **Bequest Threshold Verification:**
    $$\text{Max Allowed Bequest} = \frac{\text{Net Estate}}{3}$$
    If $\text{Wills} + \text{Sadakah} > \text{Max Allowed}$, the app applies a scale factor to cap them at the maximum boundary:
    $$\text{Scale Factor} = \frac{\text{Max Allowed Bequest}}{\text{Wills} + \text{Sadakah}}$$
3.  **Faraid Pool Allocation:** Evaluates primary fixed shares (*Ashab al-Furud*) from the final remainder.
4.  **Residue Phase:** If there is remaining wealth, it flows to the sons and daughters using the relational coefficient:
    $$\text{Daughter Share} = \frac{\text{Residue}}{(2 \times \text{Sons}) + \text{Daughters}}$$
    $$\text{Son Share} = 2 \times \text{Daughter Share}$$

---

## 🔒 Privacy & Data Policy

*   **100% Client-Side:** All computation occurs directly within the user's browser runtime.
*   **Zero External Requests:** No telemetry, tracking, backend server pings, or address data transmission are used, making it completely private and secure for sensitive financial assessments.

---

## ⚖️ Disclaimer

*This calculator provides automated breakdowns for primary heirs (Spouse, Parents, Children) based on standard Sunni legal text templates. It does not account for complex layered familial structures (e.g., distant grandparents, step-relations, or full/half-sibling exclusions under specific conditions). For official estate planning and legal executions, please consult a qualified local Islamic scholar or Shariah-compliant estate practitioner.*
