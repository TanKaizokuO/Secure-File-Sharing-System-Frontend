# SecureVault Frontend 🔒

   

**SecureVault** is a client-side interface for a secure, role-based file sharing system. Built with a focus on **Neobrutalist** design principles and the **Catppuccin** color palette, it provides a distinctive, high-contrast, and responsive UI for encrypting, uploading, and retrieving sensitive data.

This project serves as the frontend for the [SecureVault Backend API](https://www.google.com/search?q=http://localhost:8000).

## ✨ Features

  * **Hybrid Encryption Interface:** User-friendly forms to trigger encryption (Upload) and decryption (Download) processes.
  * **Role-Based Access Control (RBAC):** UI elements to specify access levels (Admin, User, Guest) and file expiration.
  * **Dynamic Vault Listing:** Real-time fetching and rendering of available encrypted packages.
  * **Neobrutalist Design:** Hard borders, bold typography (`Space Mono`), and deep drop shadows for a tactile, "raw" aesthetic.
  * **Theming Engine:**
      * 🌑 **Dark Mode:** Based on **Catppuccin Mocha**.
      * ☀️ **Light Mode:** Based on **Catppuccin Latte**.
  * **Reactive Feedback:** Built-in Toast notification system and loading spinners for API interactions.

## 🛠️ Tech Stack

  * **HTML5:** Semantic structure.
  * **CSS3:** Custom properties (variables), Grid layout, Flexbox, and CSS animations. No external CSS frameworks were used (Pure CSS).
  * **JavaScript (ES6+):** Vanilla JS for DOM manipulation, state management, and `fetch` API integration.

## 🚀 Getting Started

### Prerequisites

1.  A modern web browser (Chrome, Firefox, Edge, Safari).
2.  The **SecureVault Backend API** running locally on port `8000`.
      * *Note: If your backend is running elsewhere, see "Configuration" below.*

### Installation & Usage

1.  **Clone the Repository** (or save the file):

    ```bash
    git clone https://github.com/yourusername/securevault-frontend.git
    cd securevault-frontend
    ```

2.  **Launch the Application:**
    Since this is a static file, you can simply open `index.html` in your browser.

      * **Option A:** Double-click `index.html`.
      * **Option B (Recommended):** Serve it with a lightweight server (like Live Server or Python):
        ```bash
        # Python 3
        python -m http.server 5500
        ```
        Then visit `http://localhost:5500`.

3.  **Verify Connection:**
    Look at the "API Status" badge in the header.

      * **Green (API: ONLINE):** Connection to backend successful.
      * **Red (API: OFFLINE):** Backend is down or unreachable.

## ⚙️ Configuration

The application is configured to look for the backend at `http://localhost:8000` by default.

To change the API endpoint:

1.  Open `index.html` in a text editor.
2.  Scroll to the `<script>` tag at the bottom.
3.  Modify the `API_URL` constant:

<!-- end list -->

```javascript
// --- CONFIGURATION ---
const API_URL = 'http://your-server-ip:8000'; // Change this URL
```

## 🎨 Design System

This project strictly adheres to a **Neobrutalist** aesthetic using **Catppuccin** colors.

### Color Palette (Catppuccin Mocha)

| Color | Hex | Usage |
| :--- | :--- | :--- |
| **Base** | `#1e1e2e` | Main Background |
| **Mantle** | `#181825` | Card Backgrounds |
| **Mauve** | `#cba6f7` | Primary Buttons / Accents |
| **Sapphire**| `#74c7ec` | Secondary Accents / Info |
| **Green** | `#a6e3a1` | Success States |
| **Red** | `#f38ba8` | Error States / Delete Actions |

### Typography

  * **Font:** `Space Mono` (Google Fonts).
  * **Style:** Monospace, geometric, and highly readable.

## 📡 API Endpoints Consumed

The frontend interacts with the following backend endpoints:

  * `GET /health`: Checks system status.
  * `GET /`: Fetches API version.
  * `POST /encrypt`: Uploads file + metadata for encryption.
  * `POST /decrypt`: Requests decryption and file download.
  * `GET /packages`: Lists all available encrypted files.
  * `DELETE /packages/{id}`: Permanently deletes a file.
