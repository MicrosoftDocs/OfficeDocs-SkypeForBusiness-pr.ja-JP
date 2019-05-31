---
title: Exchange と Microsoft Teams の連携
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dstrome
description: チームの作成、チームへの参加、チャネルの作成など、Microsoft Teams と様々な Exchange のセットアップとの間に存在する機能について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 05c870dd953a0be959c59996820b3f11bf721521
ms.sourcegitcommit: e487637fc122727b41b37961f208ddc0d20a3fce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591656"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange と Microsoft Teams の連携

> [!Tip]
> Teams が Azure Active Directory (AAD)、Office 365 グループ、Exchange、SharePoint、および OneDrive for Business とどのようにやり取りするのかを学ぶために、次のセッションをご覧ください: [Microsoft Teamsの基礎](https://aka.ms/teams-foundations)。

Teams のすべての機能を活用するために、すべてのユーザーは Exchange Online、SharePoint Online、および Office 365 グループの作成が可能になっている必要があります。

ユーザーの Exchange メールボックスは、オンラインまたはオンプレミスにホストすることができます。Exchange Online または Exchange 専用 vNext にホストされるユーザーは、Teams の全機能を使用できます。チームやチャネルの作成およびそれらへの参加、会議の作成および表示、通話とチャット、ユーザー プロフィールの写真の変更、コネクタやタブ、ボットの追加と構成を行うことができます。

Exchange Online 専用 – レガシーまたは Exchange On-premises にホストされるユーザーは、Office 365 用の Azure Active Directory と同期する必要があります。 チームやチャネルの作成およびそれらへの参加、タブ、ボットの追加と構成、およびチャットや通話を行うことができます。 ただし、ユーザー プロファイルの写真を変更したり、コネクタを追加して構成したりすることはできません。 別のユーザーが構成したコネクタからメッセージを受信することができます。 メッセージの作成や表示については、条件が少し複雑です。会議の作成と表示は、Exchange 2016 累積更新プログラム 3 (CU3) 以降でサポートされますが、Exchange 2016 CU3 以前のバージョンではサポートされません。

次の表では、さまざまな環境でホストされた Exchange Online のユーザーのための情報を示します。

**サポートされるアクション:**

| ユーザーのメールボックスのホスト先: | 電子情報開示| 法的な&nbsp;保全 | 保持| チームとチャネルの管理 |会議を作成して表示する| ユーザー プロフィールの写真を変更する | 通話履歴 | 連絡先の管理 | Outlook の連絡先へのアクセス | ボイスメール |コネクタを追加して構成する|タブを追加して構成する|ボットを追加して構成する| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|はい <sup>2</sup>|はい <sup>2</sup>|可|可|可|可|可|可|可|可|可|可|可|
|**Exchange Online 専用 vNext**|はい <sup>2</sup>|はい <sup>2</sup>|可|可|可|可|可|可|可|可|可|可|可|
|**Exchange Online 専用 – レガシー** (Azure AD との同期が必要)|はい <sup>2</sup>|はい <sup>2、3</sup>|はい <sup>4|あり|なし|いいえ|はい|あり|いいえ|はい <sup>5|可|可|はい|
|**Exchange On-premises** (Azure AD との同期が必要)|はい <sup>2</sup>| はい <sup>2、3</sup> |はい <sup>4|はい|はい (Exchange 2016 CU3+)|はい (Exchange 2016 CU3+)|はい|あり|いいえ|はい <sup>5|可|可|はい|

<sup>1</sup> Exchange 2016 CU3 以降でサポートされます  
<sup>2</sup> チャネル メッセージのコンプライアンスに関する電子情報開示および法的な保全は、すべてのホスティング オプションでサポートされています。  
<sup>3</sup> Teams のプライベート チャット メッセージは、このホスティングオプションの法的な保全ではまだサポートされていません。

<sup>4</sup> 保持には、オンラインユーザーがメッセージを保存するためのシャドウ メールボックスを使用します。 [Microsoft Teamsは、Exchange ハイブリッド環境でTeamsでの電子情報開示ユーザーをサポートします](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009)。

<sup>5</sup> オンプレミスのExchangeメールボックスを持つチームユーザーは、Teamsでボイスメールを使用してOutlookでボイスメールメッセージを受信できますが、ボイスメールメッセージをTeamsクライアント内で表示または再生することはできません。

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Microsoft Teams を最大限に活用するための要件

Microsoft Teams では、さまざまな Office 365 サービスと連携して、ユーザーに充実したエクスペリエンスを提供します。 このエクスペリエンスをサポートするには、特定の機能またはサービスを有効にし、ライセンスを割り当てる必要があります。

- SharePoint Online はチームの会話でファイルを共有および保存するために必要です。 Microsoft Teams はオンプレミスの SharePoint をサポートしません。

- ユーザーがチャットでファイルを共有する場合は、SharePoint Online ライセンスが割り当てられている必要があります。 ユーザーにSharePoint Onlineの有効なライセンスが割り当てられていない場合は、Office 365にOneDrive for Businessのストレージがありません。 ファイルの共有はチャネルで引き続き機能しますが、Office 365 では OneDrive for Business の記憶域なしでチャットでファイルを共有することはできません。

- ユーザーが Microsoft Teams でチームを作成するためには、Office 365 グループの作成について有効になっている必要があります。

- Microsoft Teams で Exchange をオンプレミスで使用できるようにするには、「 [exchange と Exchange Online の間での oauth 認証の構成](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)」の説明に従って新しい Exchange OAuth 認証プロトコルを構成する必要があります。

## <a name="additional-considerations"></a>その他の考慮事項

組織に Microsoft Teams を導入する際には、次の点を考慮する必要があります。

- Microsoft Teams では、電子情報開示、コンテンツ検索、アーカイブ、訴訟ホールドのようなセキュリティおよびコンプライアンスの機能は Exchange Online と SharePoint Online の環境で最適に動作します。チャネルの会話の場合、メッセージは Exchange Online 内のグループ メールボックスにジャーナリングされます。これらのメッセージは電子情報開示で利用できます。SharePoint Online と OneDrive for Business (職場または学校のアカウントを使用) が組織全体とユーザーに対して有効な場合は、これらのコンプライアンス機能も Teams 内のすべてのファイルに対して利用できます。

- 条件付きアクセスを使用して、Teams および Exchange でのコンプライアンスポリシーの構成を制御および保護します。 詳細については、「[チームの条件付きアクセスポリシーの](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams)しくみ」を参照してください。 .

- 会議のすべてのディスカッションを検出できるようにするためのコンプライアンス要件が組織にある場合は、開催者が Exchange オンプレミスのメールボックスを使用している場合は、プライベート会議を無効にする必要があります。

- Exchangeハイブリッド展開では、チャット参加者がクラウドベースのメールボックスかオンプレミスメールボックスを持っているかにかかわらず、チャットメッセージのコンテンツを検索できます。 詳細については、[Office 365でのオンプレミスユーザーのクラウドベースメールボックスの検索](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)を参照してください。 Teams でコンテンツを検索する方法については、[Office 365セキュリティ/コンプライアンスセンターのコンテンツ検索](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)をご覧ください。

> [!TIP]
> Azure AD Connect を使用して Azure Active Directory と同期する方法については、[オンプレミス ID と Azure Active Directory の統合](https://go.microsoft.com/fwlink/?linkid=854600)をご覧ください。
