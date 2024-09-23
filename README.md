"O projeto sre_devops-stacks é uma iniciativa voltada para a criação de um portfólio abrangente de estudos e práticas relacionadas ao universo DevOps e SRE (Site Reliability Engineering). Com foco em ferramentas de código aberto e amplamente utilizadas no contexto de ambientes Linux e em plataformas de nuvem como AWS, Google Cloud Platform e Azure, este projeto reúne uma série de repositórios dedicados a aprofundar o conhecimento em tecnologias-chave.

Os repositórios são estruturados para abordar ferramentas como Python, Go, Red Hat, Git, GitLab, Docker, Kubernetes, shell scripting, Terraform, Ansible, Datadog, Prometheus, Grafana, ELK (Elasticsearch, Logstash, Kibana) e outras relevantes para a prática de SRE e DevOps.

Cada repositório contém estudos, exemplos de código, guias práticos, casos de uso e recursos que auxiliam na compreensão, implementação e otimização dessas tecnologias. O objetivo é oferecer um recurso aberto e colaborativo para entusiastas, profissionais em busca de aprimoramento e equipes interessadas em aprofundar seus conhecimentos nessas áreas fundamentais para a confiabilidade e eficiência de sistemas e aplicações.

Por meio do sre_devops-stacks, os usuários têm acesso a um conjunto valioso de informações e práticas que visam fortalecer suas habilidades técnicas e promover o desenvolvimento contínuo na área de SRE e DevOps, impulsionando a excelência na gestão de infraestrutura e operações de sistemas distribuídos e escaláveis."

FROM cgr.dev/chainguard/node:latest AS final

# Defina o diretório de trabalho
WORKDIR /evolution

# Copie os arquivos de build do estágio anterior
COPY --from=builder /evolution/dist ./dist

# Exponha a porta que o servidor usará
EXPOSE 8081

# Comando para rodar a aplicação
CMD ["node", "dist/server.js"]