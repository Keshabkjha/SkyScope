# SkyScope - Weather Intelligence Platform

<div align="center">

![SkyScope Logo](https://img.shields.io/badge/SkyScope-Weather%20Intelligence-blue?style=for-the-badge)
![React](https://img.shields.io/badge/React-19.2.4-61DAFB?style=for-the-badge&logo=react&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.8.2-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-6.2.0-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

*A sophisticated weather intelligence platform powered by AI, providing real-time weather data, forecasts, and intelligent insights through an intuitive chat interface. Now with embeddable widget support for seamless integration into any website or application.*

[View Demo](https://skyscope-phi.vercel.app/) · [Embed Demo](https://keshabkjha.github.io/ClimaSense/) · [Report Bug](https://github.com/Keshabkjha/SkyScope/issues) · [Request Feature](https://github.com/Keshabkjha/SkyScope/issues)

</div>

## 🌟 Features

- **🤖 AI-Powered Weather Chat**: Natural language conversations about weather conditions and forecasts
- **📊 Interactive Weather Maps**: Visual weather data representation with interactive mapping
- **📈 Advanced Analytics**: Temperature trends, precipitation patterns, and weather analytics
- **🌍 Global Coverage**: Weather information for locations worldwide
- **📱 Responsive Design**: Optimized for desktop, tablet, and mobile devices
- **⚡ Real-time Updates**: Live weather data with automatic refresh capabilities
- **🎯 Smart Suggestions**: Contextual weather queries and intelligent recommendations
- **💾 Local Storage**: Persistent chat history and user preferences
- **🔗 Embeddable Widget**: Easy integration into any website or application
- **🎛️ Embed Mode**: Clean, minimal interface perfect for third-party integration

## 🚀 Quick Start

### Prerequisites

- Node.js 18.0 or higher
- npm or yarn package manager
- Google AI API key (for weather intelligence features)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Keshabkjha/SkyScope.git
   cd SkyScope
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env.local
   ```
   
   Add your Google AI API key to `.env.local`:
   ```
   VITE_GOOGLE_AI_API_KEY=your_api_key_here
   ```

4. **Start the development server**
   ```bash
   npm run dev
   ```

5. **Open your browser**
   Navigate to `http://localhost:5173` to start using SkyScope.

## 📖 Usage

### Basic Weather Queries
- "What's the weather like in New York?"
- "Is it raining in London?"
- "7-day forecast for Tokyo"
- "Temperature trend for San Francisco"

### Advanced Features
- **Weather Maps**: Switch to map view for visual weather data
- **Temperature Units**: Toggle between Celsius and Fahrenheit
- **Chat History**: Your conversations are automatically saved
- **Smart Suggestions**: Get contextual weather query recommendations

## � Embedding SkyScope

SkyScope can be easily embedded into any website or application as a widget. Perfect for adding AI-powered weather intelligence to your existing projects.

### Basic Embedding

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

### Embed Parameters

- `?embed=1` or `?embed=true` - Enables embed mode
- **Auto-open**: Chat opens automatically when embedded
- **Clean UI**: Close button and launcher are hidden
- **Responsive**: Adapts to different screen sizes

### Advanced Embedding

For more control, you can use JavaScript to manage the embedded widget:

```javascript
// Create embed container
const container = document.createElement('div');
container.innerHTML = `
  <iframe
    id="skyscope-widget"
    src="https://skyscope-phi.vercel.app/?embed=1"
    title="SkyScope Weather Assistant"
    width="100%"
    height="700"
    frameborder="0"
    allow="geolocation; microphone"
    sandbox="allow-scripts allow-same-origin allow-forms"
    loading="lazy"
  ></iframe>
`;

// Add to your page
document.getElementById('weather-widget-container').appendChild(container);
```

### Security & Permissions

- **Sandboxed**: Safe iframe environment
- **Controlled Permissions**: Only requests necessary permissions
- **CORS Compliant**: Works across different domains
- **Secure**: No sensitive data exposure

### Use Cases

- **Weather Websites**: Add AI chat to traditional weather sites
- **Travel Apps**: Provide weather insights for travelers
- **Agricultural Platforms**: Weather intelligence for farming
- **Event Planning**: Weather forecasts for outdoor events
- **Educational Sites**: Interactive weather learning tools

### Live Example

See SkyScope in action at [ClimaSense](https://keshabkjha.github.io/ClimaSense/) - a weather dashboard that integrates SkyScope as an AI assistant.

## ��️ Development

### Available Scripts

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview

# Run tests (when implemented)
npm run test

# Run linting (when implemented)
npm run lint

# Type checking
npm run type-check
```

### Project Structure

```
SkyScope/
├── components/          # React components
│   ├── ChatBubble.tsx  # Chat message component
│   └── WeatherMap.tsx  # Weather map component
├── services/           # API services
│   └── geminiService.ts # Google AI integration
├── types.ts           # TypeScript type definitions
├── App.tsx            # Main application component
├── index.tsx          # Application entry point
└── vite.config.ts     # Vite configuration
```

### Technology Stack

- **Frontend**: React 19.2.4 with TypeScript
- **Build Tool**: Vite 6.2.0
- **UI Components**: Lucide React icons
- **Charts**: Recharts for data visualization
- **AI Integration**: Google Generative AI SDK
- **Styling**: CSS with modern responsive design

## 🤝 Contributing

We welcome contributions! Please read our [Contributing Guidelines](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

### Development Setup

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Run tests and ensure code quality
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

## 📝 API Reference

### Weather Service

The weather service provides access to real-time weather data and AI-powered insights:

```typescript
import { weatherService } from './services/geminiService';

// Get weather information
const weatherData = await weatherService.getWeather(location);

// Get weather forecast
const forecast = await weatherService.getForecast(location, days);
```

### Type Definitions

Key TypeScript interfaces for the application:

```typescript
interface WeatherMessage {
  id: string;
  role: MessageRole;
  text: string;
  timestamp: Date;
  data?: any;
}

interface ForecastDay {
  date: string;
  temperature: number;
  conditions: string;
  precipitation: number;
}
```

## 🧪 Testing

We are working on comprehensive test coverage. Currently, the project includes:

- Unit tests for utility functions
- Component testing for React components
- Integration tests for API services

Run tests with:
```bash
npm run test
```

## 📊 Performance

SkyScope is optimized for performance:

- **Bundle Size**: Optimized with Vite's tree-shaking
- **Loading Times**: Lazy loading for non-critical components
- **Caching**: Intelligent caching strategies for weather data
- **Responsive**: Optimized for all device sizes

## 🔒 Security

- API keys are stored securely in environment variables
- No sensitive data is exposed to the client
- Regular dependency updates and security audits
- See our [Security Policy](SECURITY.md) for more information

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Google Generative AI](https://ai.google.dev/) for powering our weather intelligence
- [OpenWeatherMap](https://openweathermap.org/) for weather data (if applicable)
- [React](https://reactjs.org/) team for the amazing framework
- [Vite](https://vitejs.dev/) team for the lightning-fast build tool

## 📞 Support

- 📧 Email: keshabkumarjha876@gmail.com
- 🐛 [Report Issues](https://github.com/Keshabkjha/SkyScope/issues)
- 💬 [Discussions](https://github.com/Keshabkjha/SkyScope/discussions)
- 📖 [Documentation](https://skyscope-phi.vercel.app/)

---

<div align="center">

**Made with ❤️ by [Keshab Kumar](https://github.com/Keshabkjha)**

[⭐ Star this repo](https://github.com/Keshabkjha/SkyScope/stargazers) · [🍴 Fork this repo](https://github.com/Keshabkjha/SkyScope/forks) · [📖 Documentation](https://skyscope-phi.vercel.app/)

</div>

