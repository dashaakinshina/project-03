ARG ELASTIC_VERSION

# https://www.docker.elastic.co/
FROM registry.rebrainme.com/devops_users_repos/965/do-30/elasticsearch:${ELASTIC_VERSION}

# Add your elasticsearch plugins setup here
# Example: RUN elasticsearch-plugin install analysis-icu
RUN elasticsearch-plugin install repository-s3
