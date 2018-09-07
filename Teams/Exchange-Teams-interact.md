---
title: Exchange と Microsoft Teams の連携
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: チームの作成、チームへの参加、チャネルの作成など、Microsoft Teams と様々な Exchange のセットアップとの間に存在する機能について説明します。
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6eb5d25fd670f3393f7fb0c19ce34730b6389b9
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23866500"
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Exchange と Microsoft Teams の連携 
=========================================

Microsoft Teams の全機能を活用するには、どのユーザーも Exchange Online、SharePoint Online、Office 365 グループの作成へのアクセスを許可されている必要があります。

ユーザーの Exchange メールボックスは、オンラインまたはオンプレミスにホストすることができます。Exchange Online または Exchange 専用 vNext にホストされるユーザーは、Teams の全機能を使用できます。チームやチャネルの作成およびそれらへの参加、会議の作成および表示、通話とチャット、ユーザー プロフィールの写真の変更、コネクタやタブ、ボットの追加と構成を行うことができます。

Exchange Online 専用 – レガシーまたは Exchange On-premises にホストされるユーザーは、Office 365 用の Azure Active Directory と同期する必要があります。 チームやチャネルの作成およびそれらへの参加、タブ、ボットの追加と構成、およびチャットや通話を行うことができます。 ただし、ユーザー プロファイルの写真を変更したり、コネクタを追加して構成したりすることはできません。 別のユーザーが構成したコネクタからメッセージを受信することができます。 メッセージの作成や表示については、条件が少し複雑です。会議の作成と表示は、Exchange 2016 累積更新プログラム 3 (CU3) 以降でサポートされますが、Exchange 2016 CU3 以前のバージョンではサポートされません。

次の表では、さまざまな環境でホストされた Exchange Online のユーザーのための情報を示します。

**サポートされるアクション:** 

| ユーザーのメールボックスのホスト先: | 証拠開示が可能| 訴訟ホールド | 保存期間| チームとチャネルの管理 |会議を作成して表示する| ユーザー プロフィールの写真を変更する | 通話履歴 | 連絡先を管理します。 | Outlook の連絡先にアクセスします。 | ボイスメール |コネクタを追加して構成する|タブを追加して構成する|ボットを追加して構成する| 
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|はい|はい|はい|あり|はい|はい|はい|はい|はい|はい|はい|はい|はい|
|**Exchange Online 専用 vNext**|はい|はい|あり|あり|あり|はい|はい|あり|はい|はい|はい|あり|はい|
|**Exchange Online 専用 – レガシー** (Azure AD との同期が必要)|([許可一覧](https://support.office.com/article/searching-cloud-based-mailboxes-for-on-premises-users-in-office-365-3f7dde1a-a8ea-4366-86da-8ee6777f357c)) を [はい] します。|なし|なし|あり|なし|なし|あり|あり|なし|[はい] (Exchange 2013 +)|なし|あり|はい|
|**Exchange On-premises** (Azure AD との同期が必要)|([許可一覧](https://support.office.com/article/searching-cloud-based-mailboxes-for-on-premises-users-in-office-365-3f7dde1a-a8ea-4366-86da-8ee6777f357c)) を [はい] します。|なし|なし|あり|[はい] (Exchange 2016 CU3 +)|なし|あり|あり|なし|[はい] (Exchange 2013 +)|なし|なし|はい|
                                                            
*\*Exchange 2016 CU3 以降でサポートされます*

追加情報:

-   Microsoft Teams はオンプレミスの SharePoint をサポートしません。

-   SharePoint Online はチームの会話でファイルを共有および保存するために必要です。

-   OneDrive for Business はプライベート チャットでファイルを共有および保存するために必要です。

-   SharePoint Online ライセンスが割り当てられていないユーザーは、Office 365 に OneDrive for Business ストレージがありません。ファイル共有はチャネル内で機能し続けますが、Office 365 に OneDrive for Business ストレージがないと、ユーザーはチャット内でファイルを共有することができません。

-   ユーザーが Microsoft Teams でチームを作成するためには、Office 365 グループの作成について有効になっている必要があります。

-   Microsoft Teams では、電子情報開示、コンテンツ検索、アーカイブ、訴訟ホールドのようなセキュリティおよびコンプライアンスの機能は Exchange Online と SharePoint Online の環境で最適に動作します。チャネルの会話の場合、メッセージは Exchange Online 内のグループ メールボックスにジャーナリングされます。これらのメッセージは電子情報開示で利用できます。SharePoint Online と OneDrive for Business (職場または学校のアカウントを使用) が組織全体とユーザーに対して有効な場合は、これらのコンプライアンス機能も Teams 内のすべてのファイルに対して利用できます。

> [!NOTE]
> すべての会議のディスカッションを検出可能にするというコンプライアンス要件が組織に対して課せられている場合、会議の開催者が Exchange オンプレミス メールボックスを利用しているならば、プライベート会議を無効にすることをお勧めします。

> [!IMPORTANT]
  マイクロソフト チームの [チャット] ボックスの一覧に含まれている会話に参加するユーザーには、チャットの会話を検索するのには管理者の Exchange オンライン (クラウド ・ ベース) のメールボックスが存在している必要があります。 チャットに参加して、クラウド ベースのメールボックスで、[チャット] ボックスの一覧の一部である会話が保存されるためです。 チャットの参加者には、Exchange Online のメールボックスが割り当てられていない、管理者を検索したり、チャットの会話の保留リストを配置することはできません。 たとえば、Exchange ハイブリッド展開の場合は、オンプレミスのメールボックスを持つユーザーありますマイクロソフト チームの [チャット] ボックスの一覧に含まれている会話に参加すること。 ただし、この例では、これらの会話からコンテンツを検索できないし、ユーザーがクラウド ベースのメールボックスを持っていないために、保留中の配置することはできません。 コンテンツの検索およびマイクロソフトのチームについての詳細については、 [Office 365 のセキュリティとコンプライアンス センターでのコンテンツの検索を実行する](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)を参照してください。

> [!TIP]
  Azure AD 接続を使用して、Azure Active Directory と同期する方法については[*、オンプレミス ユーザーは、Azure Active Directory との統合*](https://go.microsoft.com/fwlink/?linkid=854600)」を参照してください。
