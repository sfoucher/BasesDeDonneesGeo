FROM mcr.microsoft.com/devcontainers/miniconda:1-3

# Copy environment.yml (if found) to a temp location so we update the environment. Also
# copy "noop.txt" so the COPY instruction does not fail if no environment.yml exists.
COPY jupyter_env.yaml requirements.txt .devcontainer/noop.txt /tmp/conda-tmp/
RUN if [ -f "/tmp/conda-tmp/jupyter_env.yaml" ]; then umask 0002 && /opt/conda/bin/conda env update -n base -f /tmp/conda-tmp/jupyter_env.yaml; fi
#    && rm -rf /tmp/conda-tmp


# [Optional] Uncomment to install a different version of Python than the default
#RUN conda install -y python=3.10 \
#     && pip install --no-cache-dir pipx \
#     && pipx reinstall-all

#COPY environment.yml* .devcontainer/noop.txt /tmp/conda-tmp/
#RUN conda install --file /workspaces/TraitementImagesPythonVol1/requirements.txt
# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>
