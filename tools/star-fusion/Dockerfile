FROM nfcore/base

LABEL authors="rickard.hammaren@scilifelab.se, phil.ewels@scilifelab.se, martin.proks@scilifelab.se" \
    description="Docker image containing all requirements for NGI-RNAfusion pipeline"

COPY environment.yml /
RUN conda env create -f /environment.yml && conda clean -a
ENV PATH /opt/conda/envs/star-fusion/bin:$PATH

RUN apt-get install make && perl -MCPAN -e 'install Carp::Assert'
RUN ln -s /lib/x86_64-linux-gnu/libcrypt.so.1 /lib/x86_64-linux-gnu/libcrypto.so.1.0.0