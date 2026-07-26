/* =============================================================
   Hetvik Apps — main.js
   Shared behaviour for all pages
   ============================================================= */
(function () {
  "use strict";

  /* ---------- Theme (dark default, persisted) ---------- */
  var root = document.documentElement;
  var stored;
  try { stored = localStorage.getItem("hetvik-theme"); } catch (e) { stored = null; }
  if (stored === "light" || stored === "dark") {
    root.setAttribute("data-theme", stored);
  } else {
    root.setAttribute("data-theme", "dark");
  }

  function toggleTheme() {
    var next = root.getAttribute("data-theme") === "dark" ? "light" : "dark";
    root.setAttribute("data-theme", next);
    try { localStorage.setItem("hetvik-theme", next); } catch (e) {}
  }

  /* ---------- On DOM ready ---------- */
  document.addEventListener("DOMContentLoaded", function () {

    /* Theme toggle buttons */
    document.querySelectorAll("[data-theme-toggle]").forEach(function (btn) {
      btn.addEventListener("click", toggleTheme);
    });

    /* Sticky / animated navbar */
    var nav = document.querySelector(".nav");
    var toTop = document.querySelector(".to-top");
    function onScroll() {
      var y = window.scrollY || window.pageYOffset;
      if (nav) nav.classList.toggle("scrolled", y > 24);
      if (toTop) toTop.classList.toggle("show", y > 500);
    }
    onScroll();
    window.addEventListener("scroll", onScroll, { passive: true });

    /* Mobile menu */
    var burger = document.querySelector("[data-menu-toggle]");
    var menu = document.querySelector(".mobile-menu");
    if (burger && menu) {
      burger.addEventListener("click", function () {
        var open = menu.classList.toggle("open");
        burger.setAttribute("aria-expanded", open ? "true" : "false");
        var icon = burger.querySelector("i");
        if (icon) icon.className = open ? "fa-solid fa-xmark" : "fa-solid fa-bars";
      });
      menu.querySelectorAll("a").forEach(function (a) {
        a.addEventListener("click", function () {
          menu.classList.remove("open");
          var icon = burger.querySelector("i");
          if (icon) icon.className = "fa-solid fa-bars";
          burger.setAttribute("aria-expanded", "false");
        });
      });
    }

    /* Active nav link based on current file */
    var path = location.pathname.split("/").pop() || "index.html";
    document.querySelectorAll("[data-nav]").forEach(function (a) {
      if (a.getAttribute("data-nav") === path) a.classList.add("active");
    });

    /* Back to top */
    if (toTop) {
      toTop.addEventListener("click", function () {
        window.scrollTo({ top: 0, behavior: "smooth" });
      });
    }

    /* Scroll reveal */
    var revealEls = document.querySelectorAll(".reveal");
    if ("IntersectionObserver" in window && revealEls.length) {
      var io = new IntersectionObserver(function (entries) {
        entries.forEach(function (en) {
          if (en.isIntersecting) {
            en.target.classList.add("in");
            io.unobserve(en.target);
          }
        });
      }, { threshold: 0.14, rootMargin: "0px 0px -40px 0px" });
      revealEls.forEach(function (el) { io.observe(el); });
    } else {
      revealEls.forEach(function (el) { el.classList.add("in"); });
    }

    /* Animated counters */
    var counters = document.querySelectorAll("[data-count]");
    if (counters.length && "IntersectionObserver" in window) {
      var cio = new IntersectionObserver(function (entries) {
        entries.forEach(function (en) {
          if (!en.isIntersecting) return;
          animateCount(en.target);
          cio.unobserve(en.target);
        });
      }, { threshold: 0.6 });
      counters.forEach(function (c) { cio.observe(c); });
    }
    function animateCount(el) {
      var target = parseFloat(el.getAttribute("data-count"));
      var suffix = el.getAttribute("data-suffix") || "";
      var decimals = (el.getAttribute("data-decimals")) ? parseInt(el.getAttribute("data-decimals"), 10) : 0;
      var dur = 1500, start = null;
      function step(ts) {
        if (!start) start = ts;
        var p = Math.min((ts - start) / dur, 1);
        var eased = 1 - Math.pow(1 - p, 3);
        var val = target * eased;
        el.textContent = val.toFixed(decimals).replace(/\B(?=(\d{3})+(?!\d))/g, ",") + suffix;
        if (p < 1) requestAnimationFrame(step);
        else el.textContent = target.toFixed(decimals).replace(/\B(?=(\d{3})+(?!\d))/g, ",") + suffix;
      }
      requestAnimationFrame(step);
    }

    /* Card cursor glow */
    document.querySelectorAll(".card").forEach(function (card) {
      card.addEventListener("mousemove", function (e) {
        var r = card.getBoundingClientRect();
        card.style.setProperty("--mx", (e.clientX - r.left) + "px");
        card.style.setProperty("--my", (e.clientY - r.top) + "px");
      });
    });

    /* FAQ accordion */
    document.querySelectorAll(".acc-q").forEach(function (q) {
      q.addEventListener("click", function () {
        var item = q.closest(".acc-item");
        var ans = item.querySelector(".acc-a");
        var isOpen = item.classList.contains("open");
        document.querySelectorAll(".acc-item.open").forEach(function (o) {
          if (o !== item) { o.classList.remove("open"); o.querySelector(".acc-a").style.maxHeight = null; o.querySelector(".acc-q").setAttribute("aria-expanded", "false"); }
        });
        if (isOpen) {
          item.classList.remove("open");
          ans.style.maxHeight = null;
          q.setAttribute("aria-expanded", "false");
        } else {
          item.classList.add("open");
          ans.style.maxHeight = ans.scrollHeight + "px";
          q.setAttribute("aria-expanded", "true");
        }
      });
    });

    /* Contact form (front-end only) */
    var form = document.querySelector("[data-contact-form]");
    if (form) {
      form.addEventListener("submit", function (e) {
        e.preventDefault();
        var status = form.querySelector(".form-status");
        var btn = form.querySelector("button[type=submit]");
        if (btn) { btn.disabled = true; btn.dataset.old = btn.innerHTML; btn.innerHTML = '<i class="fa-solid fa-circle-notch fa-spin"></i> Sending'; }
        setTimeout(function () {
          if (status) {
            status.classList.add("show");
            var name = (form.querySelector("#name") || {}).value || "there";
            status.querySelector("span").textContent = "Thanks, " + name.split(" ")[0] + "! Your message is ready — we'll reply to your email soon.";
          }
          form.reset();
          if (btn) { btn.disabled = false; btn.innerHTML = btn.dataset.old; }
          if (status) status.scrollIntoView({ behavior: "smooth", block: "center" });
        }, 900);
      });
    }

    /* Copy buttons (app-ads.txt) */
    document.querySelectorAll("[data-copy]").forEach(function (btn) {
      btn.addEventListener("click", function () {
        var sel = btn.getAttribute("data-copy");
        var el = document.querySelector(sel);
        if (!el) return;
        var text = el.innerText.trim();
        var done = function () {
          var old = btn.innerHTML;
          btn.innerHTML = '<i class="fa-solid fa-check"></i> Copied';
          setTimeout(function () { btn.innerHTML = old; }, 1600);
        };
        if (navigator.clipboard && navigator.clipboard.writeText) {
          navigator.clipboard.writeText(text).then(done, done);
        } else {
          var ta = document.createElement("textarea");
          ta.value = text; document.body.appendChild(ta); ta.select();
          try { document.execCommand("copy"); } catch (e) {}
          document.body.removeChild(ta); done();
        }
      });
    });

    /* Current year in footer */
    document.querySelectorAll("[data-year]").forEach(function (el) {
      el.textContent = new Date().getFullYear();
    });

  });
})();
