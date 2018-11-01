---
title: Lync Server 2013 でのサーバー間認証 (Oauth) およびパートナー アプリケーションの管理
TOCTitle: Lync Server 2013 でのサーバー間認証 (Oauth) およびパートナー アプリケーションの管理
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48271778
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのサーバー間認証 (Oauth) およびパートナー アプリケーションの管理

 

_**トピックの最終更新日:** 2015-05-14_

Microsoft Lync Server 2013 は、セキュリティで保護された状態で、シームレスに、その他のアプリケーションおよびサーバー製品と通信できる必要があります。たとえば、連絡先データかアーカイブ データ、またはその両方が、Microsoft Exchange Server 2013 に保存されるように Lync Server 2013 を構成できます。しかし、これは、Lync Server と Exchange がセキュリティで保護された状態で相互に通信できる場合にのみ構成できます。同様に、Microsoft SharePoint Server から Lync Server 電話会議をスケジュール設定できます。しかし、これも、2 台のサーバー (SharePoint と Lync Server) が相互を信頼する場合にのみ設定できます。Lync から Exchange への通信にある認証メカニズムを使用し、Lync から SharePoint への通信には別のメカニズムを使用できます。より優れた、より効率的な手法は、すべてのサーバー間認証と承認で標準化された方法を使用することです。

サーバー間認証で、単一の、標準化された方式を使用することは、Lync Server 2013 の手法です。2013 リリースでは、(Exchange 2013 と Microsoft SharePoint Server を含むその他の Microsoft サーバー製品に加えて) Lync Server 2013 は、サーバー間認証および承認用に OAuth プロトコルをサポートします。OAuth は、主要なさまざまな Web サイトによって使用されている標準的な承認プロトコルで、ユーザー資格情報とパスワードはパソコン間でやり取りされません。または、認証と承認はセキュリティ トークンのやり取りに基づきます。これらのトークンが、特定の期間、特定のリソースのセットにアクセスを許可します。

OAuth 認証には、一般的には、単一の承認サーバーと、相互に通信する必要がある 2 つの領域の、3 者が関わります。(承認サーバーを使用しないで、サーバー間認証をすることもできます。この過程については、この文書で後述します。) セキュリティ トークンは、承認サーバー (セキュリティ トークン サーバーとも呼ばれます) によって、通信する必要がある 2 つの領域に発行されます。これらのトークンが、ある領域から発信された通信が、別の領域によって信頼できることを証明します。たとえば、承認サーバーは、特定の Lync Server 2013 領域からのユーザーが、指定された Exchange 2013 領域にアクセスでき、その逆もまた可能であることを証明するトークンを発行できます。

> [!NOTE]
> 領域とは、セキュリティ コンテナーのことです。既定では、Lync Server 2013 は既定の SIP ドメインを OAuth 領域として使用します。


Lync Server 2013 では、3 つのサーバー間認証シナリオをサポートしています。Lync Server 2013 では、以下の操作を実行できます。

  - Lync Server 2013 の社内インストールと、Exchange 2013 や Microsoft SharePoint Server の社内インストール間でのサーバー間認証を構成します。

  - Office 365 コンポーネントどうしのペア (Microsoft Exchange と Microsoft Lync Server、Microsoft Lync Server と Microsoft SharePoint など) 間でのサーバー間認証を構成します。

  - クロスプレミス環境 (つまり、社内サーバーと Office 365 コンポーネント間のサーバー間認証) でサーバー間認証を構成します。

この時点では、Exchange 2013、SharePoint Server、および Lync Server 2013 のみがサーバー間認証をサポートすることに注意してください。これらのサーバーのどれかを実行していない場合は、OAuth 認証を十分に実装することはできません。

サーバー間認証は必ずしも使用しなくてよいという点もご注意ください。サーバー間認証は Lync Server 2013 を展開する上で、必須ではありません。Lync Server 2013 が (Exchange 2013 のような) その他のサーバーと通信する必要がない場合は、サーバー間認証は不要です。

しかし、"統合連絡先ストア" のような、Lync Server の一部の新機能を使用する場合は、サーバー間認証は必要です。統合連絡先ストアでは、Lync Server 2013 連絡先の情報は、Lync Server ではなく Exchange 2013 内に保存されます。これにより、ユーザーは Lync、Microsoft Outlook、または Microsoft Outlook Web Access から容易に単一の連絡先を参照できます。統合連絡先ストアでは、Lync Server 2013 が Exchange 2013 と情報を共有する必要があることにより、機能を展開する目的でサーバー間認証を使用する必要があります。また、Exchange アーカイブを使用する場合も、サーバー間認証は必要です。このアーカイブでは、インスタント メッセージング セッションのチャット内容が、個別のデータベース レコードではなく、Exchange 2013 電子メールとして保存されます。

Lync Server の Office 365 バージョンが、Exchange の通信対象と通信するには、まず、Lync Server 2013 が承認サーバーからセキュリティ トークンを取得する必要があります。次に、Lync Server は、そのセキュリティ トークンを使用して、Exchange にそれ自体を識別させます。Exchange の Office 365 バージョンも、Lync Server 2013 と通信するには、同じ過程を経る必要があります。

しかし、2 つの Microsoft サーバー間の社内サーバー間認証では、サード パーティーのトークン サーバーは不要です。Lync Server 2013 や Exchange 2013 のようなサーバー製品には、組み込みのトークン サーバーがあります。これは、サーバー間認証をサポートする (SharePoint サーバーのような) その他の Microsoft サーバーで認証の目的に使用できます。たとえば、Lync Server 2013 は、それ自体がセキュリティ トークンを発行して、署名できます。次に、そのトークンを使用して Exchange 2013 と通信できます。このような場合、サード パーティーのトークン サーバーは不要です。

Lync Server 2013 の社内実装でサーバー間認証を構成するには、2 つの作業をする必要があります。

  - Lync Server の組み込みトークン発行者に証明書を割り当てます。

  - Lync Server 2013 が通信するサーバーを "パートナー アプリケーション" として構成します。たとえば、Lync Server 2013 が Exchange 2013 と通信する場合は、Exchange をパートナー アプリケーションとして構成する必要があります。

> [!NOTE]
> &quot;パートナー アプリケーション&quot; は、サードパーティのセキュリティ トークン サーバーを経由することなく、Lync Server 2013 がセキュリティ トークンを直接交換できるアプリケーションです。


OAuth は製品の中核部分なので、無効化したり削除したりすることはできません。

## 関連項目

#### 概念

[サーバー間の認証証明書の Microsoft Lync Server 2013 への割り当て](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[クロスプレミス環境での Microsoft Lync Server 2013 の構成](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)

