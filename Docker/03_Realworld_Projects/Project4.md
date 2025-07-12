# 📊 Project 4: Monitor Dockerized App with Prometheus & Grafana

## 🎯 Objective

Set up monitoring for a Dockerized application using **Prometheus** for metrics collection and **Grafana** for visualization.

---

## 🧱 Tech Stack

* **Container Platform**: Docker
* **Monitoring Tool**: Prometheus
* **Visualization**: Grafana
* **Orchestration (optional)**: Docker Compose

---

## 📁 Project Structure

```
monitoring-stack/
├── docker-compose.yml
├── prometheus/
│   └── prometheus.yml
├── app/
│   ├── main.go           # or main.py (with /metrics endpoint)
│   └── Dockerfile
```

---

## 🐳 Step 1: Dockerized App with /metrics Endpoint (Go Example)

### 📄 main.go

```go
package main

import (
  "net/http"
  "github.com/prometheus/client_golang/prometheus"
  "github.com/prometheus/client_golang/prometheus/promhttp"
)

var httpRequests = prometheus.NewCounter(
  prometheus.CounterOpts{
    Name: "http_requests_total",
    Help: "Total number of HTTP requests",
  },
)

func main() {
  prometheus.MustRegister(httpRequests)
  http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
    httpRequests.Inc()
    w.Write([]byte("Hello from monitored app!"))
  })
  http.Handle("/metrics", promhttp.Handler())
  http.ListenAndServe(":8080", nil)
}
```

### 📄 Dockerfile

```Dockerfile
FROM golang:1.21
WORKDIR /app
COPY . .
RUN go build -o app
EXPOSE 8080
CMD ["./app"]
```

---

## 🔧 Step 2: Prometheus Config (`prometheus/prometheus.yml`)

```yaml
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: 'dockerized-app'
    static_configs:
      - targets: ['app:8080']
```

---

## ⚙️ Step 3: Docker Compose File

### 📄 docker-compose.yml

```yaml
version: '3.8'

services:
  app:
    build: ./app
    ports:
      - "8080:8080"

  prometheus:
    image: prom/prometheus
    volumes:
      - ./prometheus/prometheus.yml:/etc/prometheus/prometheus.yml
    ports:
      - "9090:9090"

  grafana:
    image: grafana/grafana
    ports:
      - "3000:3000"
```

---

## 🚀 Step 4: Run the Monitoring Stack

```bash
docker-compose up --build
```

---

## 🌐 Step 5: Access Dashboards

* App → [http://localhost:8080](http://localhost:8080)
* Prometheus → [http://localhost:9090](http://localhost:9090)
* Grafana → [http://localhost:3000](http://localhost:3000) (Login: `admin` / `admin`)

### 📊 In Grafana:

1. Add Prometheus data source (`http://prometheus:9090`)
2. Import dashboard or create your own using `http_requests_total`

---

## 🧹 Step 6: Cleanup

```bash
docker-compose down
```

---

## ❓ Interview/Production Notes

* Always expose `/metrics` endpoint in apps
* Keep scrape intervals reasonable (e.g., 15s, 30s)
* In real setups, configure alerts via Alertmanager
* Secure Grafana and Prometheus endpoints in production

---

## 📌 Summary

| Step                                            | Description |
| ----------------------------------------------- | ----------- |
| ✅ Exposed /metrics endpoint in app              | ✔️          |
| ✅ Configured Prometheus                         | ✔️          |
| ✅ Visualized metrics with Grafana               | ✔️          |
| ✅ Ran full monitoring stack with Docker Compose | ✔️          |

---

