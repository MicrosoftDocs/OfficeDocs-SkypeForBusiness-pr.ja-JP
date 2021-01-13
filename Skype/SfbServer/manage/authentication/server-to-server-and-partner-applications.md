---
title: Skype for Business Server でサーバー間認証 (OAuth) とパートナー アプリケーションを管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: '概要: Skype for Business Server で OAuth とパートナー アプリケーションを管理します。'
ms.openlocfilehash: ff926440d1f00601eacfb77aadb858063b3e48b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828307"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Skype for Business Server でサーバー間認証 (OAuth) とパートナー アプリケーションを管理する
 
**概要:** Skype for Business Server で OAuth とパートナー アプリケーションを管理します。
  
Skype for Business Server は、他のアプリケーションやサーバー製品と安全かつシームレスに通信できる必要があります。 たとえば、連絡先データやアーカイブ データが 2013 年 1 月 1 日に保存Microsoft Exchange Serverできます。ただし、これは、Skype for Business Server と Exchange が互いに安全に通信できる場合にのみ実行できます。 同様に、Skype for Business Server 会議は、Web Apps サーバー Officeスケジュールできます。この場合も、2 つのサーバー (SharePoint と Skype for Business Server) が信頼している場合にのみ実行できます。 Skype for Business Server と Exchange 間の通信には 1 つの認証メカニズムを使用できますが、Skype for Business Server と SharePoint 通信の別のメカニズムを使用することもできますが、すべてのサーバー間の認証と承認に標準化された方法を使用する方が、より効率的で効率的です。
  
単一の標準化された方法でサーバー間認証を行う方法は、Skype for Business Server が採用する方法です。 Office Server 2013 リリースから、Skype for Business Server (および Exchange Server や SharePoint Server を含む他の Microsoft Server 製品) は、サーバー間の認証と承認のための OAuth (Open Authorization) プロトコルをサポートしました。 OAuth では、多数の主要な Web サイトで使用される標準的な認証プロトコルであり、ユーザー資格情報とパスワードはコンピューター間で渡されません。 代わりに、認証と承認はセキュリティ トークンの交換に基づいて行います。これらのトークンは、特定の時間の特定のリソース セットへのアクセスを許可します。
  
OAuth 認証には、通常、1 つの認証サーバーと、相互に通信する必要がある 2 つの領域という 3 つの関係者が関係します。 (認証サーバーを使用せずにサーバー間認証を行う場合も、このドキュメントで後で説明するプロセス) を実行できます。セキュリティ トークンは、認証サーバー (セキュリティ トークン サーバーとも呼ばれる) から通信が必要な 2 つの領域に発行されます。これらのトークンは、ある領域から発信された通信が他の領域によって信頼される必要があるという検証を行います。 たとえば、認証サーバーがトークンを発行して、特定の Skype for Business Server 領域のユーザーが指定された Exchange 領域にアクセスできる、またはその逆の場合があります。
  
> [!NOTE]
> 領域とは、セキュリティ コンテナーのことです。 既定では、Skype for Business Server は既定の SIP ドメインを OAuth 領域として使用します。 追加の SIP 名前空間が OAuth 証明書のサブジェクト代替名リストに追加されます。 
  
Skype for Business Server は、3 つのサーバー間認証シナリオをサポートしています。 Skype for Business Server では、次の方法を実行できます。
  
- Skype for Business Server のオンプレミス インストールと、Exchange または SharePoint Server のオンプレミス インストールとの間のサーバー間認証を構成します。
    
- Microsoft 365 または Office 365 の 2 つのコンポーネント間 (たとえば、Microsoft Exchange Server と Skype for Business Server の間、または Skype for Business Server と SharePoint の間) のサーバー間認証を構成します。
    
- クロスオンプレミス環境 (つまり、オンプレミス サーバーと Microsoft 365 または Office 365 コンポーネントの間のサーバー間認証) でサーバー間認証を構成します。
    
現時点では、Exchange 2013、SharePoint Server、Lync Server 2013、Skype for Business Server 2015、および Skype for Business 2019 だけがサーバー間認証をサポートしています。これらのサーバーのいずれかを実行していない場合は、OAuth 認証を完全に実装できません。
  
また、サーバー間認証はオプションです。Skype for Business Server が他のサーバー (Exchange など) と通信する必要はない場合は、サーバー間認証を完全にスキップできます。 Lync Server 2013 および他のアプリケーションに対してサーバー間認証が既に構成されている場合は、Skype for Business Server に対して認証を再実行する必要はありません。 
  
ただし、Skype for Business Server の一部の機能 ("統合連絡先ストア" など) を使用する場合は、サーバー間認証が必要です。 統合連絡先ストアでは、Skype for Business Server の連絡先情報は、Skype for Business Server ではなく Exchange に格納されます。これにより、ユーザーは、Skype for Business、Outlook、または Outlook Web Access 内から簡単にアクセスできる連絡先のセットを 1 つ持つ可能性があります。 統合連絡先ストアでは Skype for Business Server が Exchange と情報を共有する必要があります。このため、機能を展開するにはサーバー間認証を使用する必要があります。 また、インスタント メッセージング セッションのトランスクリプトを個別のデータベース レコードとしてではなく Exchange 電子メールとして保存する Exchange アーカイブを使用する場合も、サーバー間認証が必要です。
  
Microsoft 365 または Office 365 バージョンの Skype for Business Server が Exchange の対応するバージョンと通信するには、最初に Skype for Business Server が認証サーバーからセキュリティ トークンを取得する必要があります。 その後、Skype for Business Server はそのセキュリティ トークンを使用して Exchange に対して自身を識別します。 Microsoft 365 または Office 365 バージョンの Exchange は、Skype for Business Server と通信するために同じプロセスを実行する必要があります。
  
ただし、2 台の Microsoft サーバー間でオンプレミスのサーバー間認証を行う場合は、サードパーティのトークン サーバーを使用する必要はありません。 Skype for Business Server や Exchange などのサーバー製品には、サーバー間認証をサポートする他の Microsoft サーバー (SharePoint Server など) との認証に使用できるトークン サーバーが組み込まれています。 たとえば、Skype for Business Server はセキュリティ トークンを発行してそれ自体に署名し、そのトークンを使用して Exchange と通信できます。 このような場合、サード パーティのトークン サーバーは不要です。
  
Skype for Business Server のオンプレミス実装用にサーバー間認証を構成するには、次の 2 つの操作を行う必要があります。
  
- 組み込みの Skype for Business Server トークン発行者に証明書を割り当てる。
    
- Skype for Business Server が通信するサーバーを "パートナー アプリケーション" として構成します。 たとえば、Skype for Business Server が Exchange と通信する必要がある場合は、Exchange をパートナー アプリケーションとして構成する必要があります。
    
> [!NOTE]
> "パートナー アプリケーション" は、サード パーティのセキュリティ トークン サーバーを経由することなく、Skype for Business Server がセキュリティ トークンを直接交換できるアプリケーションです。 
  
OAuth は製品のコア部分であり、無効または削除できないことに注意してください。
  
## <a name="see-also"></a>関連項目

[サーバー間認証証明書を Skype for Business Server に割り当てる](assign-a-server-to-server-certificate.md)
  
[Skype for Business Server でハイブリッド環境を構成する](configure-a-hybrid-environment.md)
