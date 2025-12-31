# WebSocket Chat Application

A real-time chat application built with WebSockets, featuring a Fastify backend and React frontend.

## Overview

This is a learning project designed to demonstrate real-time communication using WebSockets. The application allows multiple users to connect, set a username, and exchange messages in real-time while seeing a list of currently connected users.

## Project Philosophy

- **Incremental development**: Built through small, focused iterations
- **Simplicity first**: Start with minimal features, add complexity only when needed
- **Separation of concerns**: Backend and frontend developed independently
- **Quality over speed**: Each iteration includes proper testing and documentation

## Architecture

This is a monorepo managed with npm workspaces containing two main packages:

- **`backend/`**: Fastify-based WebSocket server
- **`frontend/`**: React-based user interface

## Tech Stack

### Backend
- **Fastify**: Fast and low-overhead web framework
- **WebSocket**: Real-time bidirectional communication
- **TypeScript**: Type-safe development

### Frontend
- **React**: UI library
- **Vite**: Fast build tool and dev server
- **TypeScript**: Type-safe development

## Getting Started

### Prerequisites

- Node.js 20.x or higher
- npm 9.x or higher

### Installation

```bash
npm install
```

### Development

Run both workspaces in development mode:

```bash
npm run dev
```

### Build

Build both workspaces:

```bash
npm run build
```

### Testing

Run tests across all workspaces:

```bash
npm test
```

## Project Structure

```
.
├── backend/           # Backend workspace
├── frontend/          # Frontend workspace
├── docs/             # Documentation and iteration plans
│   ├── iterations/   # Iteration-specific documentation
│   └── templates/    # Document templates
├── package.json      # Root workspace configuration
└── README.md         # This file
```

## Development Approach

This project is developed using an iterative approach with clearly defined goals for each iteration. See `docs/iterations/` for detailed iteration plans and `TODO.md` for the current status.

Each iteration is designed to take 30-60 minutes and focuses on a single aspect of the application. Backend and frontend work are never combined in the same iteration to maintain clear separation of concerns.

## License

This is a learning project and is not licensed for production use.
