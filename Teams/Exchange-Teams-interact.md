---
title: Exchange と Microsoft Teams の連携
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: チームの作成、チームへの参加、チャネルの作成など、Microsoft Teams と様々な Exchange のセットアップとの間に存在する機能について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c251255807e1c673c672db20a85b7f56c4a64d6
ms.sourcegitcommit: 47b29c15ca3cf1676168608537613f3b841dbfcb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2019
ms.locfileid: "29992818"
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Exchange と Microsoft Teams の連携 
=========================================

> [!Tip]
> チームが Azure Active Directory (AAD)、Office 365 のグループ、Exchange、SharePoint およびビジネスのための OneDrive とどのように対話する方法については、次のセッションを監視する:[マイクロソフトのチームの基礎](https://aka.ms/teams-foundations)

Microsoft Teams の全機能を活用するには、どのユーザーも Exchange Online、SharePoint Online、Office 365 グループの作成へのアクセスを許可されている必要があります。

ユーザーの Exchange メールボックスは、オンラインまたはオンプレミスにホストすることができます。Exchange Online または Exchange 専用 vNext にホストされるユーザーは、Teams の全機能を使用できます。チームやチャネルの作成およびそれらへの参加、会議の作成および表示、通話とチャット、ユーザー プロフィールの写真の変更、コネクタやタブ、ボットの追加と構成を行うことができます。

Exchange Online 専用 – レガシーまたは Exchange On-premises にホストされるユーザーは、Office 365 用の Azure Active Directory と同期する必要があります。 チームやチャネルの作成およびそれらへの参加、タブ、ボットの追加と構成、およびチャットや通話を行うことができます。 ただし、ユーザー プロファイルの写真を変更したり、コネクタを追加して構成したりすることはできません。 別のユーザーが構成したコネクタからメッセージを受信することができます。 メッセージの作成や表示については、条件が少し複雑です。会議の作成と表示は、Exchange 2016 累積更新プログラム 3 (CU3) 以降でサポートされますが、Exchange 2016 CU3 以前のバージョンではサポートされません。

次の表では、さまざまな環境でホストされた Exchange Online のユーザーのための情報を示します。

**サポートされるアクション:** 

| ユーザーのメールボックスのホスト先: | 電子情報開示| 法的&nbsp;を保持 | 保存期間| チームとチャネルの管理 |会議を作成して表示する| ユーザー プロフィールの写真を変更する | 通話履歴 | 連絡先を管理します。 | Outlook の連絡先にアクセスします。 | ボイスメール |コネクタを追加して構成する|タブを追加して構成する|ボットを追加して構成する| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|<sup>2</sup>を [はい] します。|<sup>2</sup>を [はい] します。|可|はい|はい|はい|はい|はい|はい|はい|はい|可|はい|
|**Exchange Online 専用 vNext**|<sup>2</sup>を [はい] します。|<sup>2</sup>を [はい] します。|可|可|はい|はい|可|はい|はい|はい|可|可|可|
|**Exchange Online 専用 – レガシー** (Azure AD との同期が必要)|<sup>2</sup>を [はい] します。|<sup>2, 3</sup>を [はい] します。|はい<sup>4|あり|なし|いいえ|あり|あり|なし|なし|いいえ|あり|はい|
|**Exchange On-premises** (Azure AD との同期が必要)|<sup>2</sup>を [はい] します。| <sup>2, 3</sup>を [はい] します。 |はい<sup>4|あり|[はい] (Exchange 2016 CU3 +)|いいえ|あり|あり|なし|No <sup>5|なし|いいえ|あり|

<sup>1</sup> 2016 CU3 を交換しての上には、サポート  
<sup>2</sup>電子的証拠開示およびチャネルのメッセージでのコンプライアンスのための法的保持義務は、ホストのすべてのオプションに対してサポートされます。  
<sup>3</sup>チーム秘密のチャット メッセージは未サポートこのホスティング オプションは、法的保持義務を。

<sup>4</sup>保存メールボックスを使用シャドウ オンライン ユーザーのメッセージを格納します。 [Exchange ハイブリッド環境でチームのユーザーの Microsoft チームのサポートに電子的証拠開示](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-supports-eDiscovery-for-Teams-users-in-a/ba-p/200009)します。

<sup>5</sup>チームとオンプレミス Exchange メールボックスがボイスメールを使用して、チームとが、Outlook では、ボイス メール メッセージ、ボイスメールのメッセージが表示される場合がありますされますを表示または再生チーム クライアント内で使用できます。

追加情報:

-   Microsoft Teams はオンプレミスの SharePoint をサポートしません。

-   SharePoint Online はチームの会話でファイルを共有および保存するために必要です。

-   OneDrive for Business はプライベート チャットでファイルを共有および保存するために必要です。

-   SharePoint Online ライセンスが割り当てられていないユーザーは、Office 365 に OneDrive for Business ストレージがありません。ファイル共有はチャネル内で機能し続けますが、Office 365 に OneDrive for Business ストレージがないと、ユーザーはチャット内でファイルを共有することができません。

-   ユーザーが Microsoft Teams でチームを作成するためには、Office 365 グループの作成について有効になっている必要があります。

-   Microsoft Teams では、電子情報開示、コンテンツ検索、アーカイブ、訴訟ホールドのようなセキュリティおよびコンプライアンスの機能は Exchange Online と SharePoint Online の環境で最適に動作します。チャネルの会話の場合、メッセージは Exchange Online 内のグループ メールボックスにジャーナリングされます。これらのメッセージは電子情報開示で利用できます。SharePoint Online と OneDrive for Business (職場または学校のアカウントを使用) が組織全体とユーザーに対して有効な場合は、これらのコンプライアンス機能も Teams 内のすべてのファイルに対して利用できます。

-   設置型の交換、 [Exchange および Exchange Online 組織間で認証を構成する OAuth](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)で説明したように、OAuth を構成する必要があります。 

> [!NOTE]
> すべての会議のディスカッションを検出可能にするというコンプライアンス要件が組織に対して課せられている場合、会議の開催者が Exchange オンプレミス メールボックスを利用しているならば、プライベート会議を無効にすることをお勧めします。
> 
> [!IMPORTANT]
> Exchange ハイブリッド展開の場合は、チャット ・ メッセージの内容はチャット参加者がクラウド ベースのメールボックスまたはオンプレミスのメールボックスにあるかどうかに関係なく検索できます。 詳細については、[検索クラウド ベースのメールボックスをオンプレミス Office 365 のユーザー](https://docs.microsoft.com/en-us/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users)を参照してください。 チーム内のコンテンツを検索する方法については、 [Office 365 のセキュリティ & コンプライアンス センター内のコンテンツの検索](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups)を参照してください。
> 
> [!TIP]
> Azure AD 接続を使用して、Azure Active Directory と同期する方法については[、オンプレミス ユーザーは、Azure Active Directory との統合](https://go.microsoft.com/fwlink/?linkid=854600)」を参照してください。
