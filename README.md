📱 Floating WhatsApp Icon: A Quick Guide

In this guide, we'll walk you through how to create a floating WhatsApp icon on a website using only JavaScript. This method is perfect if you need to inject code via Google Tag Manager (GTM) and don't have direct access to the website's HTML. Let's get started! 🚀
🌟 Why a Floating WhatsApp Icon?

Adding a floating WhatsApp icon to your website can:

    Enhance customer engagement by providing an easy way for visitors to reach you.
    Boost conversion rates with instant messaging support.
    Create a seamless user experience with direct access to your WhatsApp chat.

🛠️ Step 1: Setting Up the Styles

First, we need to create some custom styles for our WhatsApp icon. These styles ensure the icon is positioned correctly and looks good across all devices.

javascript

// Create a style element for custom CSS
const style = document.createElement('style');
style.innerHTML = `
    #whatsapp-icon {
        position: fixed;
        bottom: 20px;
        right: 20px;
        width: 60px;
        height: 60px;
        background-color: #25D366;
        border-radius: 50%;
        box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);
        z-index: 1000;
        cursor: pointer;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    #whatsapp-icon svg {
        width: 35px;
        height: 35px;
    }
`;

// Append the style to the document head
document.head.appendChild(style);

This block of code creates and injects the necessary CSS styles for our floating icon.
🔧 Step 2: Adding the WhatsApp SVG Icon

Next, we'll create the floating icon itself, using an SVG of the WhatsApp logo. The SVG will be embedded directly into the page.

javascript

// Create the WhatsApp icon container
const whatsappIcon = document.createElement('div');
whatsappIcon.id = 'whatsapp-icon';

// Add the WhatsApp SVG icon
whatsappIcon.innerHTML = `
    <svg xmlns="http://www.w3.org/2000/svg" width="39" height="39" viewBox="0 0 39 39">
        <path fill="#00E676" d="M10.7 32.8l.6.3c2.5 1.5 5.3 2.2 8.1 2.2 8.8 0 16-7.2 16-16 0-4.2-1.7-8.3-4.7-11.3s-7-4.7-11.3-4.7c-8.8 0-16 7.2-15.9 16.1 0 3 .9 5.9 2.4 8.4l.4.6-1.6 5.9 6-1.5z"></path>
        <path fill="#FFF" d="M32.4 6.4C29 2.9 24.3 1 19.5 1 9.3 1 1.1 9.3 1.2 19.4c0 3.2.9 6.3 2.4 9.1L1 38l9.7-2.5c2.7 1.5 5.7 2.2 8.7 2.2 10.1 0 18.3-8.3 18.3-18.4 0-4.9-1.9-9.5-5.3-12.9zM19.5 34.6c-2.7 0-5.4-.7-7.7-2.1l-.6-.3-5.8 1.5L6.9 28l-.4-.6c-4.4-7.1-2.3-16.5 4.9-20.9s16.5-2.3 20.9 4.9 2.3 16.5-4.9 20.9c-2.3 1.5-5.1 2.3-7.9 2.3zm8.8-11.1l-1.1-.5s-1.6-.7-2.6-1.2c-.1 0-.2-.1-.3-.1-.3 0-.5.1-.7.2 0 0-.1.1-1.5 1.7-.1.2-.3.3-.5.3h-.1c-.1 0-.3-.1-.4-.2l-.5-.2c-1.1-.5-2.1-1.1-2.9-1.9-.2-.2-.5-.4-.7-.6-.7-.7-1.4-1.5-1.9-2.4l-.1-.2c-.1-.1-.1-.2-.2-.4 0-.2 0-.4.1-.5 0 0 .4-.5.7-.8.2-.2.3-.5.5-.7.2-.3.3-.7.2-1-.1-.5-1.3-3.2-1.6-3.8-.2-.3-.4-.4-.7-.5h-1.1c-.2 0-.4.1-.6.1l-.1.1c-.2.1-.4.3-.6.4-.2.2-.3.4-.5.6-.7.9-1.1 2-1.1 3.1 0 .8.2 1.6.5 2.3l.1.3c.9 1.9 2.1 3.6 3.7 5.1l.4.4c.3.3.6.5.8.8 2.1 1.8 4.5 3.1 7.2 3.8.3.1.7.1 1 .2h1c.5 0 1.1-.2 1.5-.4.3-.2.5-.2.7-.4l.2-.2c.2-.2.4-.3.6-.5s.4-.4.5-.6c.2-.4.3-.9.4-1.4v-.7s-.1-.1-.3-.2z"></path>
    </svg>
`;

// Append the WhatsApp icon to the body
document.body.appendChild(whatsappIcon);

This block adds the WhatsApp SVG directly to the page, making it a part of the website's DOM.
📲 Step 3: Making the Icon Interactive

Now, let's make the icon functional by adding a click event that opens WhatsApp in a new tab with a pre-filled message.

javascript

// Add click event to open WhatsApp chat
whatsappIcon.addEventListener('click', function() {
    const phoneNumber = '1234567890'; // Replace with your WhatsApp number in international format
    const message = 'Hello! How can I help you?'; // Optional: Pre-filled message
    const whatsappUrl = `https://wa.me/${phoneNumber}?text=${encodeURIComponent(message)}`;
    window.open(whatsappUrl, '_blank');
});

Replace 1234567890 with your WhatsApp number in international format (without the + symbol), and your icon is ready to connect you with customers!
🚀 Final Thoughts

Congratulations! 🎉 You've now created a floating WhatsApp icon using only JavaScript, making it possible to add this feature to any website via Google Tag Manager.

This simple yet effective tool will help you stay connected with your website visitors, offering them instant support and enhancing their overall experience.