# SkyScope Embedding Guide

SkyScope can be easily embedded into any website or application as a widget, providing AI-powered weather intelligence to your users.

## 🚀 Quick Start

### Basic Embed

```html
<iframe
  src="https://skyscope-phi.vercel.app/?embed=1"
  title="SkyScope Weather Assistant"
  width="450"
  height="700"
  frameborder="0"
  allow="geolocation; microphone"
  sandbox="allow-scripts allow-same-origin allow-forms"
></iframe>
```

That's it! SkyScope will automatically open in embed mode with a clean interface.

## 📋 Embed Parameters

| Parameter | Values | Description |
|-----------|--------|-------------|
| `embed` | `1`, `true` | Enables embed mode |
| `theme` | `light`, `dark` | Theme preference (optional) |
| `unit` | `celsius`, `fahrenheit` | Default temperature unit (optional) |

**Example:** `https://skyscope-phi.vercel.app/?embed=1&theme=dark&unit=fahrenheit`

## 🎨 Customization

### Responsive Design

```html
<iframe
  src="https://skyscope-phi.vercel.app/?embed=1"
  title="SkyScope Weather Assistant"
  style="width: 100%; max-width: 450px; height: 700px; border: none; border-radius: 12px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);"
  allow="geolocation; microphone"
  sandbox="allow-scripts allow-same-origin allow-forms"
></iframe>
```

### Mobile Optimization

```html
<iframe
  src="https://skyscope-phi.vercel.app/?embed=1"
  title="SkyScope Weather Assistant"
  style="width: 100vw; height: 100vh; border: none;"
  allow="geolocation; microphone"
  sandbox="allow-scripts allow-same-origin allow-forms"
></iframe>
```

## 🔧 Advanced Integration

### JavaScript Integration

```javascript
class SkyScopeWidget {
  constructor(containerId, options = {}) {
    this.container = document.getElementById(containerId);
    this.options = {
      width: '450',
      height: '700',
      theme: 'light',
      unit: 'celsius',
      ...options
    };
    this.render();
  }

  buildUrl() {
    const params = new URLSearchParams({
      embed: '1',
      ...(this.options.theme && { theme: this.options.theme }),
      ...(this.options.unit && { unit: this.options.unit })
    });
    return `https://skyscope-phi.vercel.app/?${params.toString()}`;
  }

  render() {
    const iframe = document.createElement('iframe');
    iframe.src = this.buildUrl();
    iframe.title = 'SkyScope Weather Assistant';
    iframe.width = this.options.width;
    iframe.height = this.options.height;
    iframe.frameBorder = '0';
    iframe.allow = 'geolocation; microphone';
    iframe.sandbox = 'allow-scripts allow-same-origin allow-forms';
    iframe.style.borderRadius = '12px';
    iframe.style.boxShadow = '0 4px 6px rgba(0, 0, 0, 0.1)';
    
    this.container.appendChild(iframe);
  }

  destroy() {
    this.container.innerHTML = '';
  }
}

// Usage
const widget = new SkyScopeWidget('weather-widget', {
  width: '100%',
  height: '600',
  theme: 'dark'
});
```

### React Component

```jsx
import React, { useEffect, useRef } from 'react';

const SkyScopeEmbed = ({ 
  width = '450', 
  height = '700', 
  theme = 'light', 
  unit = 'celsius',
  className = '' 
}) => {
  const iframeRef = useRef(null);

  useEffect(() => {
    const params = new URLSearchParams({
      embed: '1',
      ...(theme && { theme }),
      ...(unit && { unit })
    });
    
    if (iframeRef.current) {
      iframeRef.current.src = `https://skyscope-phi.vercel.app/?${params.toString()}`;
    }
  }, [theme, unit]);

  return (
    <iframe
      ref={iframeRef}
      title="SkyScope Weather Assistant"
      width={width}
      height={height}
      frameBorder="0"
      allow="geolocation; microphone"
      sandbox="allow-scripts allow-same-origin allow-forms"
      className={className}
      style={{
        borderRadius: '12px',
        boxShadow: '0 4px 6px rgba(0, 0, 0, 0.1)',
        border: 'none'
      }}
    />
  );
};

export default SkyScopeEmbed;
```

## 🔒 Security & Permissions

### Sandbox Attributes

SkyScope uses a sandboxed iframe with these permissions:
- `allow-scripts`: Required for the React application to function
- `allow-same-origin`: Required for local storage and user preferences
- `allow-forms`: Required for user input functionality

### Required Permissions

- `geolocation`: For location-based weather queries
- `microphone`: For voice input functionality

### Security Features

- ✅ **Sandboxed Environment**: Isolated from parent page
- ✅ **No API Key Exposure**: All API calls happen server-side
- ✅ **CORS Compliant**: Works across different domains
- ✅ **Secure Storage**: User data stored in browser's local storage only

## 📱 Best Practices

### Performance

```html
<!-- Lazy loading for better performance -->
<iframe
  src="https://skyscope-phi.vercel.app/?embed=1"
  title="SkyScope Weather Assistant"
  width="450"
  height="700"
  frameborder="0"
  loading="lazy"
  allow="geolocation; microphone"
  sandbox="allow-scripts allow-same-origin allow-forms"
></iframe>
```

### Accessibility

```html
<iframe
  src="https://skyscope-phi.vercel.app/?embed=1"
  title="SkyScope Weather Assistant - AI-powered weather chat"
  width="450"
  height="700"
  frameborder="0"
  role="application"
  aria-label="Weather chat assistant"
  allow="geolocation; microphone"
  sandbox="allow-scripts allow-same-origin allow-forms"
></iframe>
```

### Error Handling

```javascript
function loadSkyScope(containerId) {
  const container = document.getElementById(containerId);
  
  const iframe = document.createElement('iframe');
  iframe.src = 'https://skyscope-phi.vercel.app/?embed=1';
  iframe.title = 'SkyScope Weather Assistant';
  iframe.width = '450';
  iframe.height = '700';
  iframe.frameBorder = '0';
  iframe.allow = 'geolocation; microphone';
  iframe.sandbox = 'allow-scripts allow-same-origin allow-forms';
  
  iframe.onerror = () => {
    container.innerHTML = '<p>Weather assistant temporarily unavailable. Please try again later.</p>';
  };
  
  container.appendChild(iframe);
}
```

## 🎯 Use Cases

### Weather Websites
Add AI-powered weather chat to traditional weather websites for enhanced user engagement.

### Travel Applications
Provide travelers with conversational weather insights and destination-specific forecasts.

### Agricultural Platforms
Offer farmers weather intelligence for crop planning and agricultural decision-making.

### Event Planning
Help event organizers with weather forecasts for outdoor events and planning.

### Educational Platforms
Create interactive weather learning experiences for students and educators.

### E-commerce Integration
Add weather-based product recommendations for clothing, travel gear, and outdoor equipment.

## 🌍 Live Examples

### ClimaSense
A comprehensive weather dashboard that integrates SkyScope as an AI assistant.

**URL:** [https://keshabkjha.github.io/ClimaSense/](https://keshabkjha.github.io/ClimaSense/)

**Features:**
- Traditional weather display
- AI-powered weather chat
- Seamless integration
- Responsive design

## 🤝 Support

### Documentation
- [Main Repository](https://github.com/Keshabkjha/SkyScope)
- [Live Demo](https://skyscope-phi.vercel.app/)
- [API Documentation](https://github.com/Keshabkjha/SkyScope#api-reference)

### Issues & Questions
- [Report Issues](https://github.com/Keshabkjha/SkyScope/issues)
- [Feature Requests](https://github.com/Keshabkjha/SkyScope/issues)
- [Discussions](https://github.com/Keshabkjha/SkyScope/discussions)

### Contact
- 📧 Email: keshabkumarjha876@gmail.com
- 🌐 Website: [https://skyscope-phi.vercel.app/](https://skyscope-phi.vercel.app/)

---

## 📄 License

SkyScope is licensed under the MIT License. Feel free to embed and use it in your projects!

**Made with ❤️ by [Keshab Kumar](https://github.com/Keshabkjha)**
