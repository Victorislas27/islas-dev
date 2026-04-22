<template>
  <q-page class="bg-slate-50 text-slate-900 q-pb-xl font-sans">
    
    <section class="q-py-xl q-px-md max-w-1200 q-mx-auto border-bottom-light">
      <div class="row items-center q-col-gutter-xl q-py-lg">
        <div class="col-12 col-md-8">
          <div class="text-overline text-primary text-weight-bold q-mb-sm tracking-wider">Software Engineer | Team Lead</div>
          <h1 class="text-h2 text-weight-bolder q-mb-md tracking-tight">
            Víctor Hugo <span class="text-primary">Islas Limón</span>
          </h1>
          <p class="text-h5 text-grey-8 leading-relaxed q-mb-xl">
            Ingeniero especializado en el **Refactor de Arquitecturas Complejas**. Experto en ecosistemas 
            <span class="text-weight-bold text-dark">AdonisJS v6, Vue 3 y Flutter</span>, con enfoque en alta disponibilidad y normativas electrónicas.
          </p>
          
          <div class="row q-gutter-md">
            <q-btn 
              outline 
              color="primary" 
              label="GitHub" 
              icon="mdi-github"
              no-caps 
              class="q-px-lg rounded-8 text-weight-bold"
              type="a"
              href="https://github.com/Victorislas27"
              target="_blank"
            />
            <q-btn 
              outline 
              color="dark"
              label="linkedin"
              icon="mdi-linkedin"
              no-caps 
              class="q-px-lg rounded-8 text-weight-bold"
              type="a"
              href="https://www.linkedin.com/in/victor-hugo-islas-limon-852142191/"
              target="_blank"
            />
            
          </div>
        </div>
      </div>
    </section>

    <section class="q-py-xl q-px-md max-w-1200 q-mx-auto">
      <div class="row q-col-gutter-lg">
        <div v-for="stack in techStack" :key="stack.title" class="col-12 col-sm-6 col-md-3">
          <q-card flat bordered class="h-full rounded-12 bg-white">
            <q-card-section>
              <div class="text-subtitle2 text-primary text-weight-bold q-mb-sm">{{ stack.title }}</div>
              <div class="text-body2 text-grey-9 text-weight-medium">{{ stack.items }}</div>
              <q-separator q-my-sm />
              <div class="text-caption text-grey-6">{{ stack.details }}</div>
            </q-card-section>
          </q-card>
        </div>
      </div>
    </section>

    <section class="bg-dark text-white q-py-3xl q-mt-xl">
      <div class="max-w-1200 q-mx-auto q-px-md q-py-xl">
        <div class="text-overline text-info text-weight-bold q-mb-sm tracking-wider text-uppercase">
          Sistemas Empresariales en Producción
        </div>
        <h3 class="text-h3 text-weight-bold q-mt-none q-mb-md">Experiencia Corporativa</h3>
        <p class="text-h6 text-grey-5 q-mb-xl text-weight-regular max-w-800">
          Desarrollo, arquitectura y refactorización de sistemas internos y productos B2B durante mi trayectoria en la industria tecnológica.
        </p>

        <div class="row q-col-gutter-xl">
          <div v-for="project in detailedProjects" :key="project.title" class="col-12 col-md-6">
            <q-card flat class="bg-grey-9 text-white rounded-16 project-card-advanced border-grey-8 h-full">
              <q-card-section class="q-pa-xl">
                
                <div class="text-h4 text-weight-bold q-mb-md">{{ project.title }}</div>
                <div class="text-subtitle1 text-primary q-mb-md">{{ project.subtitle }}</div>
                
                <p class="text-body1 text-grey-4 q-mb-lg leading-relaxed">{{ project.description }}</p>

                <div class="text-weight-bold text-white q-mb-sm">Hitos Técnicos:</div>
                <ul class="q-pl-md text-grey-4 q-mb-lg" style="line-height: 1.6;">
                  <li v-for="feat in project.features" :key="feat" class="q-mb-xs">{{ feat }}</li>
                </ul>

                <div class="row q-gutter-xs q-mt-auto">
                  <q-chip v-for="t in project.tags" :key="t" dense color="grey-8" text-color="white" size="sm" class="q-px-sm text-weight-medium">
                    {{ t }}
                  </q-chip>
                </div>
              </q-card-section>
            </q-card>
          </div>
        </div>
      </div>
    </section>

    <section class="q-py-xl q-px-md max-w-1200 q-mx-auto text-center q-mt-xl q-mb-xl">
      <h2 class="text-h3 text-weight-bold q-mb-md">¿Hablamos de tu próximo proyecto?</h2>
      <p class="text-h6 text-grey-7 q-mb-xl max-w-600 q-mx-auto text-weight-regular">
        Disponible para liderazgo técnico y desarrollo de arquitecturas escalables.
      </p>
      <div class="column items-center q-gutter-sm">
        <span class="text-h5 text-weight-bold text-dark">victorlslas1999@gmail.com</span>
        <span class="text-h5 text-weight-bold text-dark">2227904880</span>
        <span class="text-subtitle1 text-grey-6">Puebla, México</span>
      </div>
    </section>

  </q-page>
</template>

<script setup lang="ts">
const techStack = [
  { title: 'Backend Core', items: 'AdonisJS v6, Node.js v22, Laravel', details: 'Arquitecturas Multi-DB (PostgreSQL, MySQL, SQLite), Lucid ORM, VineJS.' },
  { title: 'Frontend & UI', items: 'Vue 3, Nuxt 4, Quasar, Tailwind', details: 'Gestión de estado compleja, SSR, componentes atómicos y TypeScript.' },
  { title: 'Mobile Dev', items: 'Flutter, Dart, Provider Pattern', details: 'Desarrollo offline-first, sincronización local y consumo de APIs REST.' },
  { title: 'Data & Scraping', items: 'Cheerio, Puppeteer, pdf2pic', details: 'Procesamiento de documentos electrónicos y extracción de datos fiscales.' }
]

const detailedProjects = [
  {
    title: 'Campus FacturaTech',
    company: 'FacturaTech',
    subtitle: 'Refactor de Microservicios a Monolito Robusto',
    icon: 'hub',
    description: 'Lideré la migración estratégica de una arquitectura fragmentada en JS puro a una API centralizada bajo el patrón Repository para la plataforma interna de gestión.',
    features: [
      'Integración nativa con APIs de Zoom y Meet para control de asistencia.',
      'Sistema automatizado de generación de certificaciones PDF.',
      'Arquitectura desacoplada Frontend (Vue 3/Nuxt) y Backend (AdonisJS).'
    ],
    tags: ['TypeScript', 'AdonisJS v6', 'Nuxt 4', 'PostgreSQL']
  },
  {
    title: 'Documento Soporte (DSE)',
    company: 'IDEA15',
    subtitle: 'Cumplimiento Normativo DIAN Colombia',
    icon: 'verified_user',
    description: 'Desarrollo integral del ciclo de vida de documentos electrónicos, diseñando el backend desde la recepción JSON hasta la firma digital y almacenamiento.',
    features: [
      'Algoritmos de conversión JSON a XML bajo estándar UBL 2.1.',
      'Implementación de firma digital automatizada.',
      'Conexión simultánea a múltiples motores de base de datos.'
    ],
    tags: ['XML', 'UBL 2.1', 'Security', 'AdonisJS']
  },
  {
    title: 'Link App Móvil',
    company: 'IDEA15',
    subtitle: 'POS & Gestión de Inventarios Offline-First',
    icon: 'smartphone',
    description: 'Aplicación B2B multiplataforma diseñada para garantizar alta disponibilidad en puntos de venta con entornos de conectividad inestable.',
    features: [
      'Sincronización bidireccional de inventarios y ventas.',
      'Integración nativa de escáner de códigos de barras.',
      'Arquitectura escalable basada en el patrón Provider.'
    ],
    tags: ['Flutter', 'Dart', 'Provider', 'SQLite']
  },
  {
    title: 'pdf-rut-to-json',
    company: 'IDEA15',
    subtitle: 'Extractor de Identificación Fiscal',
    icon: 'qr_code_2',
    description: 'Microservicio corporativo avanzado para automatizar la captura de datos fiscales (RUT/NIT) a partir de documentos legales de clientes.',
    features: [
      'Decodificación de códigos QR mediante jsQR.',
      'Conversión de PDF a imágenes de alta resolución para scraping web.',
      'API-first con validación estricta vía VineJS.'
    ],
    tags: ['Node.js v22', 'Puppeteer', 'Scraping', 'TypeScript']
  }
]
</script>

<style scoped>
.font-sans { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif; }
.max-w-1200 { max-width: 1200px; }
.max-w-800 { max-width: 800px; }
.max-w-600 { max-width: 600px; }
.border-bottom-light { border-bottom: 1px solid #e2e8f0; }
.rounded-8 { border-radius: 8px; }
.rounded-12 { border-radius: 12px; }
.rounded-16 { border-radius: 16px; }
.leading-relaxed { line-height: 1.6; }
.tracking-wider { letter-spacing: 0.05em; }
.tracking-tight { letter-spacing: -0.02em; }
.border-grey-8 { border: 1px solid #424242; }

.project-card-advanced {
  transition: transform 0.3s ease, border-color 0.3s ease;
}
.project-card-advanced:hover {
  transform: translateY(-8px);
  border-color: var(--q-primary);
  box-shadow: 0 10px 30px rgba(0,0,0,0.4);
}
</style>