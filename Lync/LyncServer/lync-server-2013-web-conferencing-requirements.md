---
title: Lync Server 2013 での Web 会議の要件
TOCTitle: Lync Server 2013 での Web 会議の要件
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49115202
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Web 会議の要件

 

_**トピックの最終更新日:** 2016-12-08_

Web 会議を有効にすることにした場合、次のものを計画する必要があります。

  - Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。

  - 会議中に PowerPoint ファイルを共有するために必要な Office Web Apps サーバー との統合。

## ファイル ストア

Lync Server 2013 の Web 会議サービスでは、会議中に共有するコンテンツをファイル ストアに格納します。展開の一環として、Standard Edition サーバーまたは Enterprise Editionフロント エンド プールにファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。詳細については、「Topology Builder - Define the File Store for the Front End」を参照してください。Web 会議サービスでは、ファイル ストアにコンテンツを格納する前にコンテンツが暗号化されます。

Lync Server 2013 は、ファイル ストアとして、直接取り付け記憶域 (DAS) または記憶域ネットワーク (SAN)、分散ファイル システム (DFS) および RAID (Redundant Array of Independent Disks) 上のファイル共有の使用をサポートしています。Lync Server 展開ウィザードでファイル共有の場所を定義した後、Lync Server によってファイル共有内に次のようなフォルダー構造が作成されます。

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

次に、Web 会議サービスによって、PowerPoint スライド、ホワイトボード、ポーリング、および添付ファイルなどのコンテンツが WebServices フォルダーにある CollabContent フォルダーおよび CollabMetadata フォルダーに格納されます。

管理者は、ファイル共有に対するアクセス許可を設定して、必要な読み取りおよび書き込みのアクセスを RTC グループに付与する必要があります。


> [!WARNING]
> アクセス許可に関するエラーが発生する場合は、トポロジ ビルダーを開き、既存のトポロジをダウンロードして再公開してください。トポロジを公開することによって、ファイル共有のアクセス許可が検証され、必要に応じてリセットされます。



次の設定項目を使用すると、会議用にコンテンツを格納する方法を管理できます。

  - **ContentGracePeriod** ([Set-CsConferencingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingConfiguration) にあります) は、会議終了後、Web 会議コンテンツがサーバーに維持される期間を設定します。

  - **MaxContentStorageMb** ([Set-CsConferencingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingConfiguration) にあります) は、1 つの会議中に会議の記憶域として使用できるファイル領域の最大値を設定します。

**MaxUploadFileSizeMb** は、Lync Web App のファイル アップロード設定を制限するものではありません。Lync Web App のファイル サイズ アップロード制限は約 30MB に設定されており、IIS の web.config ファイル (/DataCollabWeb/Int\[Ext\]/Handler/web.config) によって制御されます。Lync Web App のファイル サイズ アップロード制限を構成するには、次のように web.config ファイル内の `maxRequestLength` および `maxAllowedContentLength` を更新します。

    <system.web>
        <!-- Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

web.config ファイルはフロント エンド サーバーごとに更新する必要があります。

## Office Web Apps サーバー

これらの新機能を使用するには、管理者は Office Web Apps サーバー をインストールし、Office Web Apps サーバー と通信できるように Lync Server 2013 を構成する必要があります。このドキュメントでは、Office Web Apps サーバー を使用するように Lync Server 2013 を構成する方法について説明しています。このドキュメントでは、Office Web Apps サーバー をインストールする方法については説明していません。インストールの詳細については、Microsoft Office Web Apps の展開 Web サイト (<http://go.microsoft.com/fwlink/?linkid=257525>) を参照してください。Office Web Apps サーバー の前提条件に関する詳細も記載されています。Office Web Apps サーバー は、Lync Server、SQL Server、またはその他のサーバー アプリケーションを実行していないスタンドアロン コンピューターにインストールする必要があります (対象のコンピューターにはどのバージョンの Office もインストールしないでください)。Office Web Apps サーバー の実行に使用するコンピューターには、特定のソフトウェア セット (.NET Framework 4.5、Windows PowerShell 3.0 など) もインストールされている必要があります。これらの要件および証明書と インターネット インフォメーション サービス (IIS) を構成する情報の詳細については、Microsoft Office Web Apps の展開 Website (<http://go.microsoft.com/fwlink/?linkid=257525>) を参照してください。

## 関連項目

#### 概念

[Lync Server 2013 での Web 会議の概要](lync-server-2013-web-conferencing-overview.md)  
[Web 会議の展開チェックリスト](lync-server-2013-deployment-checklist-for-web-conferencing.md)

