FROM python:3.10

RUN pip install --upgrade pip

COPY requirements.txt /tmp/requirements.txt
RUN pip install -r /tmp/requirements.txt && \
	rm /tmp/requirements.txt

# Add non-root user
RUN groupadd --gid 1000 vscode && \
    useradd --uid 1000 --gid 1000 -m vscode
## Make sure to reflect new user in PATH
ENV PATH="/home/vscode/.local/bin:${PATH}"

# Tell docker that all future commands should run as the appuser user
USER vscode