FROM mcr.microsoft.com/azure-sql-edge:1.0.6
USER root
# https://github.com/cagrin/sqlcmd-arm64
RUN mkdir -p /opt/mssql-tools/bin \
&& curl -sSL -o /opt/mssql-tools/bin/sqlcmd.c https://raw.githubusercontent.com/cagrin/sqlcmd-arm64/0.1.1/darwin/src/sqlcmd.c \
&& apt update && apt upgrade -y && apt install -y gcc \
&& gcc /opt/mssql-tools/bin/sqlcmd.c -o /opt/mssql-tools/bin/sqlcmd

FROM mcr.microsoft.com/azure-sql-edge:1.0.6
USER root
# https://docs.microsoft.com/en-us/powershell/scripting/install/install-other-linux?view=powershell-7.2#binary-archives
# https://github.com/PowerShell/PowerShell/releases
RUN curl -sSL -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v7.2.8/powershell-7.2.8-linux-arm64.tar.gz \
&& mkdir -p /opt/microsoft/powershell/7 \
&& tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/7 \
&& chmod +x /opt/microsoft/powershell/7/pwsh \
&& ln -s /opt/microsoft/powershell/7/pwsh /usr/bin/pwsh \
# https://docs.microsoft.com/en-us/sql/powershell/download-sql-server-ps-module?view=sql-server-ver15
# https://www.powershellgallery.com/packages/SqlServer
&& pwsh -Command Install-Module -Name SqlServer -RequiredVersion 21.1.18256 -Force
COPY --from=0 /opt/mssql-tools/bin/sqlcmd /opt/mssql-tools/bin/sqlcmd