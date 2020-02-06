---
title: Skype for Business Server でサーバー間認証 (OAuth) とパートナーアプリケーションを管理する
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
description: '概要: Skype for Business Server で OAuth とパートナーのアプリケーションを管理します。'
ms.openlocfilehash: d95d4f048743c6725e42e50b5025b0c906adaf53
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818749"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Skype for Business Server でサーバー間認証 (OAuth) とパートナーアプリケーションを管理する
 
**概要:** Skype for Business Server で OAuth とパートナーのアプリケーションを管理します。
  
Skype for Business Server は、安全かつシームレスに、他のアプリケーションやサーバー製品と通信できるようにする必要があります。 たとえば、連絡先データやアーカイブデータが Microsoft Exchange Server 2013 に保存されるように、Skype for Business Server を構成することができます。ただし、これを実行できるのは、Skype for Business Server と Exchange が相互に安全に通信できる場合のみです。 同様に、Office Web Apps サーバー内から Skype for Business Server 会議をスケジュール設定することもできます。この操作は、2台のサーバー (SharePoint と Skype for Business Server) が相互に信頼している場合にのみ実行できます。 Skype for Business Server と Exchange の間の通信には1つの認証メカニズムを使用できますが、Skype for Business Server と SharePoint での通信には別のメカニズムが用意されていますが、これを使用する方法は、すべてのサーバー間の認証と承認を行う標準化された方法です。
  
サーバー間認証に単一の標準化された方法を使用することは、Skype for Business Server で行われる方法です。 Office server 2013 リリースの使用を開始しました。 Skype for Business Server (および Exchange Server と SharePoint Server を含むその他の Microsoft サーバー製品) では、サーバー間認証のための OAuth (Open Authorization) プロトコルがサポートされています。承認. 多くの主要 web サイトで使用されている標準の認証プロトコルである OAuth を使用している場合、ユーザーの資格情報とパスワードは、あるコンピューターから別のコンピューターに渡されることはありません。 代わりに、認証と承認はセキュリティトークンの交換に基づいています。これらのトークンによって、特定の時間に対して特定のリソースのセットへのアクセスが許可されます。
  
OAuth 認証には、通常、単一の承認サーバーと、互いに通信する必要がある2つの領域の3つの当事者が関係します。 (このドキュメントの後半で説明するプロセスである承認サーバーを使用せずに、サーバー間認証を実行することもできます)。セキュリティトークンは、通信する必要がある2つの領域に対して、承認サーバー (セキュリティトークンサーバーとも呼ばれます) によって発行されます。これらのトークンは、あるレルムから発信された通信が他のレルムによって信頼される必要があることを確認します。 たとえば、承認サーバーは、特定の Skype for Business Server の領域のユーザーが、指定された Exchange の領域にアクセスできることを確認するトークンを発行する場合があります。
  
> [!NOTE]
> 領域とは、セキュリティ コンテナーのことです。 既定では、Skype for Business Server は既定の SIP ドメインを OAuth レルムとして使用します。 追加の SIP 名前空間が OAuth 証明書のサブジェクト代替名に追加されます。 
  
Skype for Business Server は、サーバー間の3つの認証シナリオをサポートしています。 Skype for Business Server では、次のことができます。
  
- Skype for Business Server のオンプレミスインストールと、Exchange または SharePoint Server のオンプレミスインストールとの間のサーバー間認証を構成します。
    
- 1組の Office 365 コンポーネント (たとえば、Microsoft Exchange Server と Skype for Business Server、または Skype for Business Server と SharePoint の間) 間でサーバー間認証を構成します。
    
- クロスプレミス環境でサーバー間認証を構成する (つまり、オンプレミスのサーバーと Office の365コンポーネントの間のサーバー間認証)。
    
この時点では、Exchange 2013、SharePoint Server、Lync Server 2013、Skype for business Server 2015、および Skype for Business 2019 はサーバー間認証をサポートしていることに注意してください。これらのサーバーのいずれかを実行していない場合は、OAuth 認証を完全に実装することはできません。
  
また、サーバー間認証は省略可能であることを確認する必要があります。 Skype for Business Server が他のサーバー (Exchange など) と通信する必要がない場合は、サーバー間認証を完全にスキップできます。 サーバー間認証が Lync Server 2013 および他のアプリケーション用に既に構成されている場合は、Skype for Business Server で再実行する必要はありません。 
  
ただし、「ユニファイド連絡先ストア」など、Skype for Business Server の一部の機能を使用する場合は、サーバー間認証が必要です。 統合連絡先ストアでは、skype for business server の連絡先情報は、Skype for Business Server の代わりに Exchange に保存されています。これにより、ユーザーは、Skype for Business、Outlook、または Outlook Web Access 内から簡単にアクセスできる単一の連絡先セットを使用できます。 ユニファイド連絡先ストアでは、Skype for Business Server で Exchange と情報を共有する必要があるため、機能を展開するには、サーバー間認証を使用する必要があります。 インスタントメッセージングセッションのトランスクリプトは、個別のデータベースレコードとしてではなく Exchange のメールとして保存されるため、Exchange アーカイブの使用を選択した場合は、サーバー間認証も必要になります。
  
Skype for Business Server の Office 365 バージョンで、その Exchange と通信するためには、まず承認サーバーからセキュリティトークンを取得する必要があります。 次に、Skype for Business Server がそのセキュリティトークンを使用して Exchange に対して身元を確認します。 Skype for Business Server と通信するためには、Office 365 バージョンの Exchange が同じ手順を実行している必要があります。
  
ただし、2つの Microsoft サーバー間でのオンプレミスのサーバー間認証の場合、サードパーティのトークンサーバーを使用する必要はありません。 Skype for Business Server や Exchange などのサーバー製品には、サーバー間認証をサポートする他の Microsoft サーバー (SharePoint Server など) との認証を目的として使用できる組み込みのトークンサーバーが用意されています。 たとえば、Skype for Business Server はセキュリティトークンを単独で発行して署名し、そのトークンを使用して Exchange と通信することができます。 このような場合は、サードパーティのトークンサーバーは必要ありません。
  
Skype for Business Server のオンプレミス実装用にサーバー間認証を構成するには、次の2つの操作を行う必要があります。
  
- 組み込みの Skype for Business Server トークンの発行者に証明書を割り当てます。
    
- Skype for Business Server が「パートナーアプリケーション」として通信するサーバーを構成します。 たとえば、Skype for Business Server が Exchange と通信する必要がある場合は、パートナーアプリケーションとして Exchange を構成する必要があります。
    
> [!NOTE]
> "パートナーアプリケーション" は、サードパーティのセキュリティトークンサーバーを経由せずに、Skype for Business Server がセキュリティトークンを直接交換できるアプリケーションです。 
  
OAuth は製品の中核部分なので、無効化したり削除したりすることはできません。
  
## <a name="see-also"></a>関連項目

[サーバー間認証証明書を Skype for Business Server に割り当てる](assign-a-server-to-server-certificate.md)
  
[Skype for Business Server でハイブリッド環境を構成する](configure-a-hybrid-environment.md)
