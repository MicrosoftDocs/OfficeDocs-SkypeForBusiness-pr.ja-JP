---
title: Skype for Business Server でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: '概要: Skype for Business Server で OAuth およびパートナーアプリケーションを管理します。'
ms.openlocfilehash: f784dd0a2dab05fb3b97497fab7d3866dda1a753
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221671"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Skype for Business Server でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理
 
**概要:** Skype for Business Server で OAuth およびパートナーアプリケーションを管理します。
  
Skype for Business Server は、安全かつシームレスに、他のアプリケーションやサーバー製品と通信できる必要があります。 たとえば、Skype for Business Server を構成して、連絡先データやアーカイブデータを Microsoft Exchange Server 2013 に保存することができます。ただし、これは、Skype for Business Server と Exchange が相互に安全に通信できる場合にのみ実行できます。 同様に、Office Web Apps サーバー内で Skype for Business Server 会議をスケジュールすることもできます。この操作は、2台のサーバー (SharePoint と Skype for business Server) が相互に信頼している場合にのみ実行できます。 Skype for business Server と Exchange との間で通信に1つの認証メカニズムを使用することは可能ですが、Skype for business Server と SharePoint の通信には別のメカニズムを使用することもできますが、すべてのサーバー間の認証と承認に対して標準化された方法を使用することをお勧めします。
  
単一の標準化された方法を使用してサーバー間認証を実行することは、Skype for Business Server による方法です。 Office Servers 2013 リリースで開始された Skype for Business Server (および Exchange Server および SharePoint Server を含むその他の Microsoft Server 製品) は、サーバー間の認証と承認のために OAuth (オープン認証) プロトコルをサポートしていました。 OAuth では、多くの主要な web サイトで使用される標準の認証プロトコルであるコンピューターから別のコンピューターにユーザーの資格情報とパスワードが渡されることはありません。 代わりに、認証と承認はセキュリティトークンの交換に基づいています。これらのトークンは、特定の時間に特定のリソースのセットへのアクセスを許可します。
  
OAuth 認証には、通常、1つの承認サーバーと、互いに通信する必要がある2つの領域の3つの関係者が関与します。 (このドキュメントで後述するプロセスを使用して、認証サーバーを使用せずにサーバー間認証を実行することもできます)。セキュリティトークンは、通信する必要がある2つの領域に対して、認証サーバー (セキュリティトークンサーバーとも呼ばれる) によって発行されます。これらのトークンは、あるレルムから発信された通信が他のレルムによって信頼されることを確認します。 たとえば、認証サーバーは、特定の Skype for Business Server 領域のユーザーが指定された Exchange 領域にアクセスできることを確認するトークンを発行することがあります。また、その逆もあります。
  
> [!NOTE]
> 領域とは、セキュリティ コンテナーのことです。 既定では、Skype for Business Server は既定の SIP ドメインを OAuth 領域として使用します。 その他の SIP 名前空間は、OAuth 証明書のサブジェクト代替名リストに追加されます。 
  
Skype for Business Server は、3つのサーバー間認証シナリオをサポートします。 Skype for Business Server を使用すると、次のことができます。
  
- Skype for Business Server のオンプレミスインストールと、Exchange および/または SharePoint Server の社内インストールとの間でサーバー間認証を構成します。
    
- Microsoft 365 または Office 365 の各コンポーネント (たとえば、Microsoft Exchange Server と Skype for business Server、または Skype for Business Server と SharePoint の間) との間でサーバー間認証を構成します。
    
- クロスプレミス環境 (つまり、オンプレミスサーバーと Microsoft 365 または Office 365 コンポーネントの間のサーバー間認証) でサーバー間認証を構成します。
    
この時点では、Exchange 2013、SharePoint Server、Lync Server 2013、Skype for Business Server 2015、および Skype for business 2019 のみがサーバー間認証をサポートすることに注意してください。これらのサーバーのいずれかを実行していない場合、OAuth 認証を完全に実装することはできません。
  
また、サーバー間認証はオプションであることを指摘する必要があります。 Skype for Business Server が他のサーバー (Exchange など) と通信する必要がない場合は、サーバー間認証を完全にスキップできます。 サーバー間認証が Lync Server 2013 およびその他のアプリケーション用に既に構成されている場合、Skype for Business Server に対して再実行する必要はありません。 
  
ただし、「統合連絡先ストア」など、Skype for Business Server の一部の機能を使用する場合は、サーバー間認証が必要です。 統合連絡先ストアの場合、Skype for business Server の連絡先情報は、Skype for Business Server ではなく Exchange に保存されます。これにより、ユーザーは、Skype for Business、Outlook、または Outlook Web Access 内から簡単にアクセスできる単一の連絡先セットを使用できるようになります。 統合連絡先ストアでは、Exchange と情報を共有するために Skype for Business Server が必要なため、機能を展開するには、サーバー間認証を使用する必要があります。 Exchange アーカイブを使用することを選択した場合は、サーバー間認証も必要になります。これにより、インスタントメッセージングセッションのトランスクリプトは、個別のデータベースレコードとしてではなく Exchange メールとして保存されます。
  
Skype for business server の Microsoft 365 または Office 365 バージョンが、対応する Exchange と通信するには、最初に承認サーバーからセキュリティトークンを取得する必要があります。 その後、Skype for Business Server は、そのセキュリティトークンを使用して Exchange に対して自分自身を識別します。 Microsoft 365 または Office 365 のバージョンの Exchange は、同じプロセスを使用して Skype for Business Server と通信する必要があります。
  
ただし、2つの Microsoft サーバー間でのオンプレミスのサーバー間認証の場合は、サードパーティのトークンサーバーを使用する必要はありません。 Skype for Business Server や Exchange などのサーバー製品には、サーバー間認証をサポートする他の Microsoft サーバー (SharePoint Server など) との認証のために使用できる組み込みのトークンサーバーがあります。 たとえば、Skype for Business Server はセキュリティトークンを単独で発行して署名し、そのトークンを使用して Exchange と通信することができます。 このような場合、サード パーティのトークン サーバーは不要です。
  
Skype for Business Server のオンプレミス実装に対してサーバー間認証を構成するには、次の2つの作業を行う必要があります。
  
- 組み込みの Skype for business Server トークン発行者に証明書を割り当てます。
    
- Skype for Business Server が通信するサーバーを、"パートナーアプリケーション" として構成します。 たとえば、Skype for Business Server が Exchange と通信する必要がある場合は、Exchange をパートナーアプリケーションとして構成する必要があります。
    
> [!NOTE]
> "パートナーアプリケーション" は、サードパーティのセキュリティトークンサーバーを使用せずに、Skype for Business Server が直接セキュリティトークンを交換できるアプリケーションです。 
  
OAuth は製品のコア部分であり、無効化または削除することはできないことに注意してください。
  
## <a name="see-also"></a>関連項目

[サーバー間認証証明書を Skype for Business Server に割り当てる](assign-a-server-to-server-certificate.md)
  
[Skype for Business Server でハイブリッド環境を構成する](configure-a-hybrid-environment.md)
