# 🚀 AI Workflow Builder

[![React](https://img.shields.io/badge/React-18.3.1-61dafb?logo=react)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.6.2-3178c6?logo=typescript)](https://www.typescriptlang.org/)
[![React Flow](https://img.shields.io/badge/React_Flow-12.3.4-ff0072)](https://reactflow.dev/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> A powerful, visual no-code platform for building and executing AI-powered workflows with drag-and-drop simplicity.

<img width="1909" height="868" alt="image" src="https://github.com/user-attachments/assets/48790f65-3863-43db-bed3-7382e2a05aaf" />

## ✨ Features

### 🎨 Visual Workflow Design
- **Drag-and-Drop Interface**: Intuitive node-based workflow creation using React Flow
- **Real-time Canvas**: Interactive visual editor with pan, zoom, and node manipulation
- **Smart Connections**: Connect nodes with conditional and sequential edges
- **Dark/Light Mode**: Toggle between themes for comfortable working in any environment

### 🧠 AI-Powered Nodes
- **Input Nodes**: Define workflow entry points with custom data
- **Prompt Nodes**: Configure AI prompts with system instructions, user messages, and temperature settings
- **Output Nodes**: Capture and display workflow results
- **Conditional Routing**: Branch workflows based on AI responses

### ⚙️ Advanced Configuration
- **Node Editor**: Comprehensive editor for customizing node properties
  - System prompts and user prompts
  - Model selection (GPT-4o, Claude, etc.)
  - Temperature controls for output randomness
  - Custom labels and metadata
- **Edge Editor**: Configure connection types and conditions
  - Default sequential connections
  - Conditional branches with custom logic
  - Visual condition labels

### 🔄 Workflow Execution
- **Real-time Execution**: Run workflows with custom input JSON
- **Visual Feedback**: See execution status and results instantly
- **Error Handling**: Comprehensive error messages and debugging info
- **Result Display**: Pretty-printed JSON output with syntax highlighting

### 📊 Workflow Management
- **Node Count Tracking**: Monitor workflow complexity
- **Edge Visualization**: Colored, labeled connections for easy understanding
- **Mini Map**: Navigate large workflows with ease
- **Background Grid**: Professional canvas with customizable patterns

## 🎯 Use Cases

- **Customer Support Automation**: Route inquiries to specialized AI agents
- **Content Generation Pipelines**: Chain multiple AI models for complex outputs
- **Data Processing Workflows**: Extract, transform, and analyze text data
- **Multi-step AI Reasoning**: Build complex decision trees with AI logic
- **A/B Testing AI Prompts**: Compare different prompt strategies visually

## 📸 Screenshots

### Main Canvas
<img width="957" height="429" alt="image" src="https://github.com/user-attachments/assets/ac6add0e-a861-466b-8e99-122219a8cb96" />
*Drag-and-drop interface with real-time node connections*

### Node Configuration
<img width="202" height="239" alt="image" src="https://github.com/user-attachments/assets/2bad8e66-e3cb-4be8-aecf-7408bfc1435b" />

*Comprehensive node editor with AI model settings*

### Workflow Execution
<img width="176" height="194" alt="image" src="https://github.com/user-attachments/assets/0d46e0c1-bbe4-4041-b9aa-11b950112649" />

*Real-time execution with JSON input/output*

## 🚀 Quick Start

### Prerequisites

- **Node.js** 18.x or higher
- **npm** or **yarn** package manager
- **Backend API** (see https://github.com/harshitbansal184507/backend-workflow-builder )

### Installation

1. **Clone the repository**
```bash
git clone (https://github.com/harshitbansal184507/frontend-workflow-builder.git)
cd workflow-builder
```

2. **Install dependencies**
```bash
npm install
# or
yarn install
```

3. **Configure environment variables**
```bash
cp .env.example .env
```

Edit `.env` and set your configuration:
```env
VITE_API_URL=http://127.0.0.1:8000
```

4. **Start the development server**
```bash
npm run dev
# or
yarn dev
```

5. **Open your browser**
```
http://localhost:5173
```

## 🛠️ Backend Setup

The frontend requires a backend API to execute workflows. Set up the backend server:



### API Endpoints
```
POST /api/workflow/execute
  - Execute a workflow with given input
  - Request body: WorkflowRequest
  - Response: WorkflowResponse

POST /api/workflow/validate
  - Validate workflow structure
  - Request body: WorkflowRequest
  - Response: ValidationResult
```

### Example Backend Response
```json
{
  "workflow": {
    "nodes": [
      {
        "id": "string",
        "type": "string",
        "data": {
          "additionalProp1": {}
        },
        "position": {
          "additionalProp1": 0,
          "additionalProp2": 0,
          "additionalProp3": 0
        }
      }
    ],
    "edges": [
      {
        "id": "string",
        "source": "string",
        "target": "string",
        "type": "default",
        "data": {}
      }
    ]
  },
  "input": {
    "additionalProp1": {}
  }
}

```

## 🏗️ Project Structure

```
ai-workflow-builder/
├── src/
│   ├── components/
│   │   └── Flow/
│   │       ├── Controls/
│   │       │   ├── NodeEditor.tsx      # Node configuration panel
│   │       │   ├── EdgeEditor.tsx      # Edge configuration panel
│   │       │   └── SidePanel.tsx       # Workflow control panel
│   │       ├── CustomNodes/            # Custom node implementations
│   │       └── CustomEdges/            # Custom edge implementations
│   ├── constants/
│   │   └── nodeTypes.ts                # Node type definitions
│   ├── services/
│   │   └── api.ts                      # API communication layer
│   ├── types/
│   │   └── workflow.types.ts           # TypeScript type definitions
│   ├── utils/
│   │   └── workflowSerializer.ts       # Workflow serialization
│   ├── App.tsx                         # Main application component
│   ├── main.tsx                        # Application entry point
│   └── index.css                       # Global styles
├── public/                             # Static assets
├── .env.example                        # Environment variables template
├── package.json                        # Project dependencies
├── tsconfig.json                       # TypeScript configuration
├── vite.config.ts                      # Vite configuration
└── README.md                           # This file
```

## 🎮 How to Use

### Creating Your First Workflow

1. **Add Input Node**
   - Click "Input" in the side panel
   - This is your workflow's starting point

2. **Add Prompt Node**
   - Click "Prompt" in the side panel
   - Click the node to open the editor
   - Configure system prompt, user prompt, and model

3. **Add Output Node**
   - Click "Output" in the side panel
   - This captures your workflow results

4. **Connect Nodes**
   - Drag from one node's output handle to another's input
   - Configure edge conditions if needed

5. **Execute Workflow**
   - Enter input JSON in the execution panel
   - Click "Execute"
   - View results in real-time

### Advanced Features

**Conditional Routing**
```
Classifier Node → TECHNICAL → Technical Support
                → BILLING → Billing Department
```

**Variable Interpolation**
Use `{{variable}}` syntax in prompts to inject input data:
```
User Prompt: "Analyze this message: {{message}}"
```



## 🧪 Development

### Available Scripts

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview

# Type checking
npm run type-check

# Linting
npm run lint
```

### Tech Stack

- **Frontend Framework**: React 18 with TypeScript
- **Workflow Engine**: React Flow 12
- **Styling**: Tailwind CSS
- **Build Tool**: Vite
- **State Management**: React Hooks (useState, useCallback)
- **HTTP Client**: Fetch API

### Code Style

This project follows:
- ESLint for code quality
- TypeScript strict mode
- Functional React components with hooks
- Component-based architecture

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### How to Contribute

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Commit your changes** (`git commit -m 'Add amazing feature'`)
4. **Push to the branch** (`git push origin feature/amazing-feature`)
5. **Open a Pull Request**

### Development Setup for Contributors

```bash
# Fork and clone
git clone https://github.com/yourusername/ai-workflow-builder.git

# Create a branch
git checkout -b feature/my-new-feature

# Install dependencies
npm install

# Start development
npm run dev

# Run tests (if applicable)
npm test
```

## 📝 Configuration

### Node Types Configuration

Add new node types in `src/constants/nodeTypes.ts`:

```typescript
{
  type: "custom",
  label: "Custom Node",
  description: "Your custom node description",
  defaultData: { /* default properties */ },
  color: "#ff6b6b"
}
```

### Supported AI Models

- GPT-4o
- GPT-4o-mini
- GPT-3.5-turbo
- Claude 3 Opus
- Claude 3 Sonnet

Add more models in `DEFAULT_MODELS` array in `nodeTypes.ts`.

## 🐛 Troubleshooting

### Common Issues

**Backend Connection Error**
```
Error: Failed to connect to backend API
```
- Ensure backend server is running
- Check `VITE_API_URL` in `.env`
- Verify CORS settings on backend

**Workflow Execution Fails**
```
Error: Workflow execution failed
```
- Validate workflow structure (all nodes connected)
- Check input JSON format
- Ensure API keys are configured on backend

**Nodes Not Rendering**
- Clear browser cache
- Check browser console for errors
- Verify React Flow dependencies are installed

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [React Flow](https://reactflow.dev/) - Powerful flow diagram library
- [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
- [Vite](https://vitejs.dev/) - Next generation frontend tooling
- OpenAI & Anthropic - AI model providers

## ⭐ Star History

If you find this project useful, please consider giving it a star!


---

<p align="center">
  Made with ❤️ by the AI Workflow Builder Team
</p>

<p align="center">
  <a href="[https://github.com/yourusername/ai-workflow-builder](https://github.com/harshitbansal184507/frontend-workflow-builder.git)">⭐ Star us on GitHub</a> •
  <a href="CONTRIBUTING.md">🤝 Contribute</a> •
  <a href="https://github.com/harshitbansal184507/frontend-workflow-builder">🐛 Report Bug</a> •
  <a href="https://github.com/harshitbansal184507/frontend-workflow-builder/issues">💡 Request Feature</a>
</p>
