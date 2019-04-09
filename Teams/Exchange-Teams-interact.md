---
title: Exchange と Microsoft Teams の連携
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: crowe
description: チームの作成、チームへの参加、チャネルの作成など、Microsoft Teams と様々な Exchange のセットアップとの間に存在する機能について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 560e1f81db6e8150bcd8d686747bfb297cbfcf84
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30569983"
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Exchange と Microsoft Teams の連携 
=========================================

> [!Tip]
> Teams がAzure Active Directory（AAD）、Office 365グループ、Exchange、SharePoint、およびOneDrive for Businessとどのようにやり取りするのかを学ぶために、次のセッションをご覧ください: [Microsoft Teamsの基礎](https://aka.ms/teams-foundations)。

Microsoft Teams の全機能を活用するには、どのユーザーも Exchange Online、SharePoint Online、Office 365 グループの作成へのアクセスを許可されている必要があります。

ユーザーの Exchange メールボックスは、オンラインまたはオンプレミスにホストすることができます。Exchange Online または Exchange 専用 vNext にホストされるユーザーは、Teams の全機能を使用できます。チームやチャネルの作成およびそれらへの参加、会議の作成および表示、通話とチャット、ユーザー プロフィールの写真の変更、コネクタやタブ、ボットの追加と構成を行うことができます。

Exchange Online 専用 – レガシーまたは Exchange On-premises にホストされるユーザーは、Office 365 用の Azure Active Directory と同期する必要があります。 チームやチャネルの作成およびそれらへの参加、タブ、ボットの追加と構成、およびチャットや通話を行うことができます。 ただし、ユーザー プロファイルの写真を変更したり、コネクタを追加して構成したりすることはできません。 別のユーザーが構成したコネクタからメッセージを受信することができます。 メッセージの作成や表示については、条件が少し複雑です。会議の作成と表示は、Exchange 2016 累積更新プログラム 3 (CU3) 以降でサポートされますが、Exchange 2016 CU3 以前のバージョンではサポートされません。

次の表では、さまざまな環境でホストされた Exchange Online のユーザーのための情報を示します。

**サポートされるアクション:** 

| ユーザーのメールボックスのホスト先: | 電子情報開示| 法的な&nbsp;保全 | 保持| チームとチャネルの管理 |会議を作成して表示する| ユーザー プロフィールの写真を変更する | 通話履歴 | 連絡先を管理します | Outlook の連絡先にアクセスします | ボイスメール |コネクタを追加して構成する|タブを追加して構成する|ボットを追加して構成する| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|はい <sup>2</sup>|はい <sup>2</sup>|はい|はい|はい|はい|はい|はい|はい|はい|はい|はい|はい|
|**Exchange Online 専用 vNext**|はい <sup>2</sup>|はい <sup>2</sup>|はい|はい|はい|はい|はい|はい|はい|はい|はい|はい|はい|
|**Exchange Online 専用 – レガシー** (Azure AD との同期が必要)|はい <sup>2</sup>|はい <sup>2,3</sup>|はい <sup>4|はい|いいえ|いいえ|はい|はい|いいえ|はい <sup>5|はい|はい|はい|
|**Exchange On-premises** (Azure AD との同期が必要)|はい <sup>2</sup>| はい <sup>2,3</sup> |はい <sup>4|はい|はい (Exchange 2016 CU3+)|はい (Exchange 2016 CU3+)|はい|はい|いいえ|はい <sup>5|はい|はい|はい|

<sup>1</sup> Exchange 2016 CU3 以降でサポートされます  
<sup>2</sup>チャネルメッセージのコンプライアンスに関する電子情報開示および法的な保全は、すべてのホスティングオプションでサポートされています。  
<sup>3</sup>Teamsのプライベートチャットメッセージは、このホスティングオプションの法的な保全ではまだサポートされていません。

<sup>4</sup> 保持には、オンラインユーザーがメッセージを保存するためのシャドウメールボックスを使用します。 [Microsoft Teamsは、Exchange ハイブリッド環境でTeamsでの電子情報開示ユーザーをサポートします](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009)。

<sup>5</sup> オンプレミスのExchangeメールボックスを持つチームユーザーは、Teamsでボイスメールを使用してOutlookでボイスメールメッセージを受信できますが、ボイスメールメッセージをTeamsクライアント内で表示または再生することはできません。

追加情報: 

-   Microsoft Teams はオンプレミスの SharePoint をサポートしません。

-   SharePoint Online はチームの会話でファイルを共有および保存するために必要です。

-   OneDrive for Business はプライベート チャットでファイルを共有および保存するために必要です。

-   SharePoint Online ライセンスが割り当てられていないユーザーは、Office 365 に OneDrive for Business ストレージがありません。ファイル共有はチャネル内で機能し続けますが、Office 365 に OneDrive for Business ストレージがないと、ユーザーはチャット内でファイルを共有することができません。

-   ユーザーが Microsoft Teams でチームを作成するためには、Office 365 グループの作成について有効になっている必要があります。

-   Microsoft Teams では、電子情報開示、コンテンツ検索、アーカイブ、訴訟ホールドのようなセキュリティおよびコンプライアンスの機能は Exchange Online と SharePoint Online の環境で最適に動作します。チャネルの会話の場合、メッセージは Exchange Online 内のグループ メールボックスにジャーナリングされます。これらのメッセージは電子情報開示で利用できます。SharePoint Online と OneDrive for Business (職場または学校のアカウントを使用) が組織全体とユーザーに対して有効な場合は、これらのコンプライアンス機能も Teams 内のすべてのファイルに対して利用できます。

-   オンプレミスのExchangeの場合は、[ExchangeとExchange Onlineの組織間のOAuth認証の構成](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)の説明に従って、新しいExchange OAuth認証プロトコルを構成する必要があります。 

> [!NOTE]
> 現在、すべての会議のディスカッションを確実に検出できるというコンプライアンス要件が組織にある場合、開催者にExchangeオンプレミスメールボックスがある場合は、プライベート会議を無効にする必要があります。
> 
> [!IMPORTANT]
> Exchangeハイブリッド展開では、チャット参加者がクラウドベースのメールボックスかオンプレミスメールボックスを持っているかにかかわらず、チャットメッセージのコンテンツを検索できます。 詳細については、[Office 365でのオンプレミスユーザーのクラウドベースメールボックスの検索](https://docs.microsoft.com/ja-JP/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)を参照してください。 Teams でコンテンツを検索する方法については、[Office 365セキュリティ/コンプライアンスセンターのコンテンツ検索](https://docs.microsoft.com/ja-JP/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)をご覧ください。
> 
> [!TIP]
> Azure AD Connect を使用して Azure Active Directory と同期する方法については、[オンプレミス ID と Azure Active Directory の統合](https://go.microsoft.com/fwlink/?linkid=854600)をご覧ください。
