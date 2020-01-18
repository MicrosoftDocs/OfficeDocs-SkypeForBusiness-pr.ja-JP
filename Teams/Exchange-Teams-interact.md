---
title: Exchange と Microsoft Teams の連携
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: チームの作成、チームへの参加、チャネルの作成など、Microsoft Teams と様々な Exchange のセットアップとの間に存在する機能について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c3f0b5c545f1a7e8900c01a79544079ea4fedcc
ms.sourcegitcommit: bcac0d94f6eb7132fc17b0ace62e7028f77b0ee6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2020
ms.locfileid: "41230317"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Exchange と Microsoft Teams の連携

> [!Tip]
> Teams が Azure Active Directory (AAD)、Office 365 グループ、Exchange、SharePoint、および OneDrive for Business とどのようにやり取りするのかを学ぶために、次のセッションをご覧ください: [Microsoft Teamsの基礎](https://aka.ms/teams-foundations)。

Teams のすべての機能を活用するために、すべてのユーザーは Exchange Online、SharePoint Online、および Office 365 グループの作成が可能になっている必要があります。

ユーザーの Exchange メールボックスは、オンラインまたはオンプレミスでホストすることができます。 ただし、一部の機能では、Office 365 テナントの代わりにハイブリッド展開を行う必要があります。

Exchange Online または Exchange 専用 vNext でホストされているユーザーは、Teams のすべての機能を使用できます。 チームとチャネルの作成と参加、会議の作成と表示、電話とチャット、ユーザープロファイルの画像の変更、コネクタ、タブ、ボットの追加と構成を行うことができます。

Exchange Online 専用 (レガシ) でホストされているユーザーは、Office 365 上の Azure Active Directory と同期する必要があります。 チームとチャネルの作成と参加、タブとボットの追加と構成、チャットと通話機能の利用などを行うことができます。 ただし、プロフィール画像の変更、会議の管理、outlook の連絡先へのアクセス、コネクタの管理はできません。

オンプレミスでホストされているメールボックスを持つユーザーは、Azure Active Directory と同期する必要があります。 上記のシナリオのすべての機能を使用できるようになりましたが、ユーザープロファイル画像の変更や会議の管理を行うこともできます。また、Exchange Server 2016 (累積更新プログラム 3) 以上がオンプレミスで実行されています。

次の表は、Exchange 環境に基づいた機能の可用性についてのクイックリファレンスです。


**サポートされるアクション:**

| ユーザーのメールボックスのホスト先: | 電子情報開示| 法的な&nbsp;保全 | 保持| チームとチャネルの管理 |Teams で会議を作成して表示する| ユーザー プロフィールの写真を変更する | 通話履歴 | 連絡先の管理 | Outlook の連絡先へのアクセス | ボイスメール |コネクタを追加して構成する|タブを追加して構成する|ボットを追加して構成する| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|はい <sup>2</sup>|はい <sup>2</sup>|Yes|Yes|Yes|Yes|Yes|Yes|○ ( <sup>7</sup> )|Yes|Yes|Yes|Yes|
|**Exchange Online 専用 vNext**|はい <sup>2</sup>|はい <sup>2</sup>|Yes|Yes|Yes|Yes|Yes|Yes|○ ( <sup>7</sup> )|Yes|Yes|Yes|はい|
|**Exchange Online 専用 – レガシー** (Azure AD との同期が必要)|はい <sup>2</sup>|はい <sup>2、3</sup>|はい <sup>4|あり|なし|いいえ|はい|あり|いいえ|はい <sup>5|はい<sup>6|Yes|Yes|
|**Exchange on-premises** (Azure AD との同期が必要)|はい <sup>2</sup>| はい <sup>2、3</sup> |はい <sup>4|はい|はい (Exchange 2016 CU3+)|はい (Exchange 2016 CU3+)|はい|あり|いいえ|はい <sup>5|はい<sup>6|Yes|Yes|

<sup>1</sup> EXCHANGE 2016 cu3 以降で以上がサポートされています。  

<sup>2</sup> チャネル メッセージのコンプライアンスに関する電子情報開示および法的な保全は、すべてのホスティング オプションでサポートされています。

<sup>3</sup> Teams のプライベート チャット メッセージは、このホスティングオプションの法的な保全ではまだサポートされていません。

<sup>4</sup> 保持には、オンラインユーザーがメッセージを保存するためのシャドウ メールボックスを使用します。 [Microsoft Teamsは、Exchange ハイブリッド環境でTeamsでの電子情報開示ユーザーをサポートします](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009)。

<sup>5</sup>チームのオンプレミス Exchange メールボックスを使用している場合、Outlook でボイスメールを使用してボイスメールメッセージを受信することはできますが、音声メッセージは、teams クライアント内で表示または再生できません。

<sup>6</sup>チームの所有者のいずれかがコネクタを追加できる場合、そのチーム内の他のユーザーは、メールボックスがオンプレミスの場合でも、その操作を行うことができます。

既定の連絡先フォルダーに含まれる連絡先が<sup>7</sup>人のみ 他の連絡先フォルダーまたはサブフォルダーへのアクセスはサポートされていません。

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Microsoft Teams を最大限に活用するための要件

Microsoft Teams では、さまざまな Office 365 サービスと連携して、ユーザーに充実したエクスペリエンスを提供します。 このエクスペリエンスをサポートするには、特定の機能またはサービスを有効にし、ライセンスを割り当てる必要があります。

- SharePoint Online はチームの会話でファイルを共有および保存するために必要です。 Microsoft Teams はオンプレミスの SharePoint をサポートしません。

- ユーザーがチャットでファイルを共有する場合は、SharePoint Online ライセンスが割り当てられている必要があります。 ユーザーにSharePoint Onlineの有効なライセンスが割り当てられていない場合は、Office 365にOneDrive for Businessのストレージがありません。 ファイルの共有はチャネルで引き続き機能しますが、Office 365 では OneDrive for Business の記憶域なしでチャットでファイルを共有することはできません。

- ユーザーが Microsoft Teams でチームを作成するためには、Office 365 グループの作成について有効になっている必要があります。

- Microsoft Teams で Exchange をオンプレミスで使用できるようにするには、「 [exchange と Exchange Online の間での oauth 認証の構成](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)」の説明に従って新しい Exchange OAuth 認証プロトコルを構成する必要があります。

> [!NOTE]
>Exchange のオンプレミスとチームの統合の場合、必要なライセンスを AAD の同期されたユーザーに割り当てる必要があります。

> [!IMPORTANT]
> ユーザーを**チーム専用**モードに移行した後に Skype for business クライアントをアンインストールすると、Outlook やその他の Office アプリでプレゼンスが停止することがあります。 プレゼンスは Teams では正常に機能します。 この問題を解決するには、Microsoft Teams の右上隅にある自分のプロファイル写真を選択し、[**設定**] を選択します。 [**全般**] タブの [**アプリケーション**] で、[ **office のチャットアプリとして Teams を登録する (office アプリケーションの再起動が必要)**] を選択します。 このオプションを選択したら、Outlook を含むすべての Office アプリを閉じて、もう一度開きます。 Outlook を起動すると、プレゼンス情報を利用できるようになります。

## <a name="additional-considerations"></a>その他の考慮事項

組織に Microsoft Teams を導入する際には、次の点を考慮する必要があります。

- Microsoft Teams では、電子情報開示、コンテンツ検索、アーカイブ、訴訟ホールドのようなセキュリティおよびコンプライアンスの機能は Exchange Online と SharePoint Online の環境で最適に動作します。チャネルの会話の場合、メッセージは Exchange Online 内のグループ メールボックスにジャーナリングされます。これらのメッセージは電子情報開示で利用できます。SharePoint Online と OneDrive for Business (職場または学校のアカウントを使用) が組織全体とユーザーに対して有効な場合は、これらのコンプライアンス機能も Teams 内のすべてのファイルに対して利用できます。

- 条件付きアクセスを使用して、Teams および Exchange でのコンプライアンスポリシーの構成を制御および保護します。 詳細については、「[チームの条件付きアクセスポリシーの](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams)しくみ」を参照してください。 .

- 会議のすべてのディスカッションを検出できるようにするためのコンプライアンス要件が組織にある場合は、開催者が Exchange オンプレミスのメールボックスを使用している場合は、プライベート会議を無効にする必要があります。

- Exchangeハイブリッド展開では、チャット参加者がクラウドベースのメールボックスかオンプレミスメールボックスを持っているかにかかわらず、チャットメッセージのコンテンツを検索できます。 詳細については、[Office 365でのオンプレミスユーザーのクラウドベースメールボックスの検索](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)を参照してください。 Teams でコンテンツを検索する方法については、[Office 365セキュリティ/コンプライアンスセンターのコンテンツ検索](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)をご覧ください。

> [!TIP]
> Azure AD Connect を使用して Azure Active Directory と同期する方法については、[オンプレミス ID と Azure Active Directory の統合](https://go.microsoft.com/fwlink/?linkid=854600)をご覧ください。
