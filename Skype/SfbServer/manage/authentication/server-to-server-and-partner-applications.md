---
title: サーバー間認証 (OAuth) とパートナー アプリケーションを管理Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: '概要: OAuth アプリケーションとパートナー アプリケーションを管理するには、Skype for Business Server。'
---

# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>サーバー間認証 (OAuth) とパートナー アプリケーションを管理Skype for Business Server
 
**概要:** OAuth とパートナー アプリケーションを管理するには、Skype for Business Server。
  
Skype for Business Serverアプリケーションやサーバー製品と安全かつシームレスに通信できる必要があります。 たとえば、連絡先データやアーカイブ データが Microsoft Exchange Server 2013 に格納されるSkype for Business Server を構成できます。ただし、この処理は、Skype for Business Server および Exchange 間で安全に通信できます。 同様に、Office Web Apps Server 内から Skype for Business Server 会議をスケジュールすることもできます。この場合も、2 つのサーバー (SharePoint と Skype for Business Server) が信頼している場合にのみ実行できます。 Skype for Business Server と Exchange 間の通信には 1 つの認証メカニズムを使用できますが、Skype for Business ServerとSharePoint 通信を行う場合は、サーバー間のすべての認証と承認に標準化された方法を使用する方が、より効率的な方法です。
  
サーバー間認証に 1 つの標準化された方法を使用する方法は、サーバー間認証で行Skype for Business Server。 Office Server 2013 リリースから開始し、Skype for Business Server (Exchange Server および SharePoint Server を含む他の Microsoft Server 製品) は、サーバー間認証と承認のための OAuth (Open Authorization) プロトコルをサポートしました。 OAuth を使用すると、多数の主要な Web サイトで使用される標準的な承認プロトコル、ユーザー資格情報、およびパスワードは、あるコンピューターから別のコンピューターに渡されません。 代わりに、認証と承認はセキュリティ トークンの交換に基づいて行います。これらのトークンは、特定の時間の特定のリソース セットへのアクセスを許可します。
  
OAuth 認証には、通常、1 つの承認サーバーと、相互に通信する必要がある 2 つの領域の 3 つの関係者が関係します。 (認証サーバーを使用せずにサーバー間認証を実行することもできます。このドキュメントで後で説明するプロセス)。セキュリティ トークンは、通信が必要な 2 つの領域に認証サーバー (セキュリティ トークン サーバーとも呼ばれる) によって発行されます。これらのトークンは、ある領域から発信される通信が他の領域によって信頼される必要があるという検証を行います。 たとえば、認証サーバーは、特定の Skype for Business Server 領域のユーザーが指定された領域にアクセスできるExchangeトークンを発行する場合があります。その逆も同様です。
  
> [!NOTE]
> 領域とは、セキュリティ コンテナーのことです。 既定では、Skype for Business Server SIP ドメインを OAuth 領域として使用します。 追加の SIP 名前空間が OAuth 証明書のサブジェクト代替名リストに追加されます。 
  
Skype for Business Serverは、3 つのサーバー間認証シナリオをサポートしています。 このSkype for Business Server、次の方法を使用できます。
  
- Skype for Business Server のオンプレミス インストールと、Exchange または SharePoint Server のオンプレミス インストールとの間でサーバー間認証を構成します。
    
- Microsoft 365 または Office 365 コンポーネントのペア間 (Microsoft Exchange Server と Skype for Business Server の間など) の間でサーバー間認証を構成するSkype for Business ServerとSharePoint)。
    
- サーバー間認証をクロスオンプレミス環境で構成します (つまり、オンプレミス サーバーと Microsoft 365 または Office 365 コンポーネント間のサーバー間認証)。
    
現時点では、Exchange 2013、SharePoint Server、Lync Server 2013、Skype for Business Server 2015、および Skype for Business 2019 はサーバー間認証をサポートします。これらのサーバーのいずれかを実行していない場合は、OAuth 認証を完全に実装できません。
  
また、サーバー間認証は省略可能です。Skype for Business Server が他のサーバー (Exchange など) と通信する必要がない場合は、サーバー間認証を完全にスキップできます。 Lync Server 2013 および他のアプリケーション用にサーバー間認証が既に構成されている場合は、サーバー間認証を実行する必要Skype for Business Server。 
  
ただし、"統合連絡先ストア" など、Skype for Business Server の一部の機能を使用する場合は、サーバー間認証が必要です。 統合連絡先ストアを使用すると、Skype for Business Server 連絡先情報は Skype for Business Server ではなく Exchange に格納されます。これにより、ユーザーは Skype for Business 内から簡単にアクセスできる 1 つの連絡先セットを持Skype for BusinessOutlook、または web Access Outlookを使用します。 統合連絡先ストアでは Skype for Business Server とExchange情報を共有する必要があります。この機能を展開するには、サーバー間認証を使用する必要があります。 Exchange アーカイブを使用する場合は、サーバー間認証も必要です。この場合、インスタント メッセージング セッションのトランスクリプトは、個々のデータベース レコードとしてではなく Exchange メールとして保存されます。
  
Microsoft 365または Office 365 バージョンの Skype for Business Serverと通信するにはExchange、Skype for Business Server 最初に認証サーバーからセキュリティ トークンを取得する必要があります。 Skype for Business Server、そのセキュリティ トークンを使用して、セキュリティ トークンを識別Exchange。 このMicrosoft 365またはOffice 365と通信するにはExchange同じプロセスを実行する必要Skype for Business Server。
  
ただし、2 台の Microsoft サーバー間でオンプレミスのサーバー間認証を行う場合は、サード パーティトークン サーバーを使用する必要はありません。 Skype for Business Server や Exchange などのサーバー製品には、サーバー間認証をサポートする他の Microsoft サーバー (SharePoint Server など) との認証目的で使用できるトークン サーバーが組み込まれています。 たとえば、セキュリティ トークンSkype for Business Server発行して署名し、そのトークンを使用してセキュリティ トークンと通信Exchange。 このような場合、サード パーティのトークン サーバーは不要です。
  
サーバー間認証を構成して、Skype for Business Serverのオンプレミス実装を構成するには、次の 2 つの操作を実行する必要があります。
  
- 証明書を組み込みのトークン発行Skype for Business Server割り当てる。
    
- "パートナー アプリケーションSkype for Business Server通信するサーバーを構成します。 たとえば、Skype for Business Serverと通信するExchange、パートナー アプリケーションExchange構成する必要があります。
    
> [!NOTE]
> "パートナー アプリケーション" は、サードパーティSkype for Business Serverを経由することなく、セキュリティ トークンを直接交換できるアプリケーションです。 
  
OAuth は製品のコア部分であり、無効または削除できないことに注意してください。
  
## <a name="see-also"></a>関連項目

[サーバー間認証証明書をサーバー間認証証明書に割り当Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[ハイブリッド環境を構成Skype for Business Server](configure-a-hybrid-environment.md)
