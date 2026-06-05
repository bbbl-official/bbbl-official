
</div>

### Technical Breakdown:

| Component | Technology | Why We Chose It |
|-----------|-----------|-----------------|
| **Edge Runtime** | Cloudflare Workers | 300+ global PoPs, cold start <5ms |
| **Protocol** | WebSocket + HTTP/3 | Bypasses most DPI systems |
| **Encryption** | AES-256-GCM + ChaCha20 | Military-grade, undetectable |
| **Routing** | Dynamic Smart Routing | Auto-selects fastest path |
| **Cache** | Edge Cache + D1 | 80% request served from cache |

<br/>

## 💀 **TECH STACK - THE ARSENAL**

<div align="center">

### LANGUAGES WE BREATHE

<img src="https://skillicons.dev/icons?i=js,ts,rust,go,python,cpp,java,kotlin,swift,php,ruby,zig,odin,crystal,elixir,erlang,haskell,scala,clojure,lua,perl,r,dart,assembly,fortran,zig,mojo,gleam,v,typst" width="100%"/>

<br/>

### FRAMEWORKS & TOOLS

<img src="https://skillicons.dev/icons?i=react,vue,angular,nextjs,nuxtjs,svelte,tailwind,nodejs,deno,bun,express,fastapi,django,spring,flutter,reactnative,electron,tensorflow,pytorch,redis,postgres,mysql,mongodb,supabase,firebase,grafana,prometheus,nginx,docker,kubernetes,terraform,ansible,githubactions,jenkins,figma,webpack,vite,rollup,esbuild,swc,babel,jest,vitest,cypress,playwright" width="100%"/>

<br/>

### CLOUD & INFRASTRUCTURE

<img src="https://skillicons.dev/icons?i=cloudflare,aws,gcp,azure,vercel,netlify,heroku,flyio,railway,koyeb,digitalocean,linode,ovh,cloudfront,lambda,s3,ec2,rds,dynamodb,firestore,workers,pages,d1,r2,queues" width="100%"/>

</div>

<br/>

## 📈 **PERFORMANCE METRICS**

<div align="center">

| Metric | Value |
|--------|-------|
| ⚡ **Average Response Time** | <100ms |
| 🌍 **Global PoPs** | 300+ |
| 📊 **Daily Requests** | 2M+ |
| 🔒 **Security Score** | A+ (SSL Labs) |
| 🚫 **Block Rate** | <0.01% |
| 💾 **Zero-Logging** | ✅ Guaranteed |

</div>

<br/>

## 🎯 **THE ARCHITECTURE**

```mermaid
graph TB
  subgraph "Edge Layer - Cloudflare Workers"
      A[Request Router]
      B[Auth/Payload]
      C[Smart Routing]
  end
  
  subgraph "Processing"
      D[Decrypt Payload]
      E[Fetch Target]
      F[Rewrite Response]
  end
  
  subgraph "Storage"
      G[(D1 Analytics)]
      H[KV Cache]
      I[R2 Static]
  end
  
  User --> A
  A --> B
  B --> C
  C --> D
  D --> E
  E --> F
  F --> User
  E -.-> G
  C -.-> H
  A -.-> I
  
  style A fill:#141416,stroke:#fff
  style B fill:#141416,stroke:#fff
  style C fill:#141416,stroke:#fff
  style D fill:#141416,stroke:#fff
  style E fill:#141416,stroke:#fff
  style F fill:#141416,stroke:#fff
