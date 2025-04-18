<script setup lang="ts">
// Get current year for copyright
const currentYear = new Date().getFullYear()
</script>

<template>
  <footer class="site-footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-logo">
          <a href="#" class="logo-text">MapleStory</a>
          <p class="footer-tagline">Begin Your Epic Adventure</p>
        </div>
        
        <div class="footer-links">
          <div class="footer-section">
            <h4>Game Info</h4>
            <ul>
              <li><a href="#">Classes</a></li>
              <li><a href="#">Worlds</a></li>
              <li><a href="#">Systems</a></li>
              <li><a href="#">Updates</a></li>
            </ul>
          </div>
          
          <div class="footer-section">
            <h4>Community</h4>
            <ul>
              <li><a href="#">Forums</a></li>
              <li><a href="#">Discord</a></li>
              <li><a href="#">Rankings</a></li>
              <li><a href="#">Events</a></li>
            </ul>
          </div>
          
          <div class="footer-section">
            <h4>Support</h4>
            <ul>
              <li><a href="#">Help Center</a></li>
              <li><a href="#">Account Security</a></li>
              <li><a href="#">Billing</a></li>
              <li><a href="#">Contact Us</a></li>
            </ul>
          </div>
          
          <div class="footer-section">
            <h4>Connect</h4>
            <div class="social-links">
              <a href="#" class="social-icon">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M24 4.557c-.883.392-1.832.656-2.828.775 1.017-.609 1.798-1.574 2.165-2.724-.951.564-2.005.974-3.127 1.195-.897-.957-2.178-1.555-3.594-1.555-3.179 0-5.515 2.966-4.797 6.045-4.091-.205-7.719-2.165-10.148-5.144-1.29 2.213-.669 5.108 1.523 6.574-.806-.026-1.566-.247-2.229-.616-.054 2.281 1.581 4.415 3.949 4.89-.693.188-1.452.232-2.224.084.626 1.956 2.444 3.379 4.6 3.419-2.07 1.623-4.678 2.348-7.29 2.04 2.179 1.397 4.768 2.212 7.548 2.212 9.142 0 14.307-7.721 13.995-14.646.962-.695 1.797-1.562 2.457-2.549z" />
                </svg>
              </a>
              <a href="#" class="social-icon">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z" />
                </svg>
              </a>
              <a href="#" class="social-icon">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M22.046 0h-20.092c-1.089 0-1.954.865-1.954 1.954v20.092c0 1.089.865 1.954 1.954 1.954h20.092c1.089 0 1.954-.865 1.954-1.954v-20.092c0-1.089-.865-1.954-1.954-1.954zm-15.046 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z" />
                </svg>
              </a>
              <a href="#" class="social-icon">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z" />
                </svg>
              </a>
            </div>
          </div>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p class="copyright">&copy; {{ currentYear }} MapleStory. All Rights Reserved.</p>
        <div class="footer-legal">
          <a href="#">Privacy Policy</a>
          <a href="#">Terms of Service</a>
          <a href="#">EULA</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.site-footer {
  background-color: var(--color-neutral-900);
  color: var(--color-neutral-300);
  padding-top: var(--space-12);
  padding-bottom: var(--space-6);
}

.footer-content {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--space-8);
  margin-bottom: var(--space-8);
  border-bottom: 1px solid var(--color-neutral-700);
  padding-bottom: var(--space-8);
}

.footer-logo {
  text-align: center;
}

.logo-text {
  font-family: var(--font-heading);
  font-weight: 800;
  font-size: var(--font-size-2xl);
  color: white;
  margin-bottom: var(--space-2);
  display: inline-block;
}

.footer-tagline {
  color: var(--color-neutral-400);
  font-size: var(--font-size-md);
}

.footer-links {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  gap: var(--space-8);
}

.footer-section h4 {
  color: white;
  margin-bottom: var(--space-4);
  font-size: var(--font-size-lg);
}

.footer-section ul {
  list-style: none;
  padding: 0;
}

.footer-section li {
  margin-bottom: var(--space-2);
}

.footer-section a {
  color: var(--color-neutral-400);
  transition: color var(--transition-fast) var(--transition-function);
}

.footer-section a:hover {
  color: white;
}

.social-links {
  display: flex;
  gap: var(--space-3);
}

.social-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: var(--radius-full);
  background-color: var(--color-neutral-800);
  color: var(--color-neutral-300);
  transition: all var(--transition-normal) var(--transition-function);
}

.social-icon svg {
  width: 20px;
  height: 20px;
}

.social-icon:hover {
  background-color: var(--color-primary-600);
  color: white;
  transform: translateY(-3px);
}

.footer-bottom {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: var(--space-4);
}

.copyright {
  color: var(--color-neutral-500);
  font-size: var(--font-size-sm);
}

.footer-legal {
  display: flex;
  gap: var(--space-4);
  flex-wrap: wrap;
  justify-content: center;
}

.footer-legal a {
  color: var(--color-neutral-500);
  font-size: var(--font-size-sm);
  transition: color var(--transition-fast) var(--transition-function);
}

.footer-legal a:hover {
  color: var(--color-neutral-300);
}

@media (min-width: 640px) {
  .footer-links {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr 2fr;
    text-align: left;
  }
  
  .footer-logo {
    text-align: left;
  }
  
  .footer-bottom {
    flex-direction: row;
    justify-content: space-between;
  }
}

@media (min-width: 1024px) {
  .footer-links {
    grid-template-columns: repeat(4, 1fr);
  }
}
</style>