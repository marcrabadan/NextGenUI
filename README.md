# NextJS Project Builder

## Overview

`nextjs_project_builder.js` is a script that automates the creation of a Next.js project, including the setup of pages, CSS libraries, and optional integration with OpenAI for content generation. This project is designed with best practices in mind, utilizing principles such as SOLID to maintain code clarity and extensibility.

## Features

- Create a Next.js project using JavaScript or TypeScript.
- Automatically install specified CSS libraries (e.g., Tailwind CSS).
- Generate pages with customizable content.
- Use OpenAI to generate content based on user-defined prompts.
- Supports the integration of UI design systems through YAML configuration.

## Prerequisites

- Node.js and npm installed.
- A valid OpenAI API key for content generation (optional).

## Installation

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```

2. Install the dependencies:
   ```bash
   npm install
   ```

## Usage

### Step 1: Create a Configuration File

Create a YAML file (`site_structure.yaml`) with the desired configuration for your project. Here is an example:

```yaml
project:
  name: "MyNextJsProject"
  language: "typescript" # Can be "javascript" or "typescript"
  css_libraries:
    - tailwindcss
  design_system: "ui_design_system.yaml"

pages:
  - name: home
    path: "/"
    prompt: "Design a welcoming homepage."
    components:
      - type: hero
        translations:
          en:
            title: "Welcome to Our Website"
            subtitle: "Explore our amazing platform."
          es:
            title: "Bienvenidos a Nuestra Web"
            subtitle: "Explora nuestra increíble plataforma."
        image: "/images/hero.jpg"
      - type: features
        translations:
          en:
            title: "Our Features"
            items:
              - "Feature 1: High Performance"
              - "Feature 2: Easy to Use"
              - "Feature 3: Secure"
          es:
            title: "Nuestras Características"
            items:
              - "Característica 1: Alto Rendimiento"
              - "Característica 2: Fácil de Usar"
              - "Característica 3: Seguro"

  - name: about
    path: "/about"
    prompt: "Design an about page with information about the company."
    components:
      - type: section
        translations:
          en:
            title: "Our Story"
            content: "We started in 2010 and have grown quickly."
          es:
            title: "Nuestra Historia"
            content: "Comenzamos en 2010 y hemos crecido rápidamente."
      - type: team
        translations:
          en:
            title: "Meet Our Team"
            members:
              - name: "John Doe"
                role: "CEO"
                bio: "John has over 20 years of experience in the tech industry."
              - name: "Jane Smith"
                role: "CTO"
                bio: "Jane is passionate about technology and innovation."
          es:
            title: "Conoce a Nuestro Equipo"
            members:
              - name: "John Doe"
                role: "CEO"
                bio: "John tiene más de 20 años de experiencia en la industria tecnológica."
              - name: "Jane Smith"
                role: "CTO"
                bio: "Jane es apasionada por la tecnología y la innovación."

  - name: contact
    path: "/contact"
    prompt: "Design a contact page with a simple form."
    components:
      - type: form
        translations:
          en:
            title: "Contact Us"
          es:
            title: "Contáctanos"
        fields:
          - name: name
            translations:
              en: "Name"
              es: "Nombre"
            type: text
          - name: email
            translations:
              en: "Email"
              es: "Correo Electrónico"
            type: email
          - name: message
            translations:
              en: "Message"
              es: "Mensaje"
            type: textarea
```

### Step 2: Set OpenAI API Key (Optional)

If you want to generate content with OpenAI, set your API key as an environment variable:

```bash
export OPENAI_API_KEY=your_openai_api_key
```

### Step 3: Run the Script

Run the script to create the Next.js project based on the provided YAML configuration:

```bash
node nextjs_project_builder.js site_structure.yaml
```

## How It Works

1. **YamlLoader**: Loads the configuration from the YAML file.
2. **NextJsProject**: Handles the creation of the Next.js project and loads the design system if provided.
3. **CssLibraryInstaller**: Installs the specified CSS libraries (e.g., Tailwind CSS).
4. **OpenAIContentGenerator**: Uses OpenAI API to generate content based on the provided prompt.
5. **PageGenerator**: Creates the pages for the Next.js project, either using manually defined components or generating content with OpenAI.

## Example Configuration

You can extend the `ui_design_system.yaml` file to define your design system:

```yaml
design_system:
  themes:
    - name: light
      colors:
        primary: "#0070f3"
        background: "#ffffff"
  typography:
    font_family: "'Roboto', sans-serif"
    font_sizes:
      header: "2rem"
      title: "1.5rem"
      description: "1rem"
      button: "1rem"
  components:
    button:
      padding: "10px 20px"
      border_radius: "4px"
      spacing: "8px"
      colors:
        light:
          background: "#0070f3"
          text: "#ffffff"
        dark:
          background: "#0f62fe"
          text: "#ffffff"
    card:
      padding: "16px"
      border_radius: "8px"
      shadow: "lg"
      colors:
        light:
          background: "#ffffff"
          border: "#e5e7eb"
        dark:
          background: "#1f2937"
          border: "#374151"
    grid:
      columns: 12
      gutter: "16px"
    spacing:
      small: "8px"
      medium: "16px"
      large: "32px"

  header:
    height: "80px"
    padding: "16px"
    colors:
      light:
        background: "#ffffff"
        text: "#0070f3"
      dark:
        background: "#121212"
        text: "#0f62fe"
```

## License

This project is licensed under the MIT License.

## Contributing

Contributions are welcome! Feel free to submit a pull request or open an issue.

## Contact

For questions or suggestions, please reach out to [marc.rabadan@gmail.com].

