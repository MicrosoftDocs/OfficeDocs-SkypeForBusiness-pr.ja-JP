---
title: "Exchange と Microsoft Teams の連携 | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "チームの作成、チームへの参加、チャネルの作成など、Microsoft Teams と様々な Exchange のセットアップとの間に存在する機能について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: a7d3bed465d1a13e35bbbe92c5fd2b8237e199b9
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2017
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Exchange と Microsoft Teams の連携 
=========================================

Microsoft Teams の全機能を活用するには、どのユーザーも Exchange Online、SharePoint Online、Office 365 グループの作成へのアクセスを許可されている必要があります。

ユーザーの Exchange メールボックスは、オンラインまたはオンプレミスにホストすることができます。Exchange Online または Exchange 専用 vNext にホストされるユーザーは、Microsoft Teams の全機能を使用できます。チームやチャネルの作成およびそれらへの参加、会議の作成および表示、ユーザー プロフィールの写真の変更、コネクタやタブ、ボットの追加と構成、およびチャットや通話を行うことができます。

Exchange Online 専用 – レガシーまたは Exchange On-premises にホストされるユーザーは、Office 365 用の Azure Active Directory と同期する必要があります。チームやチャネルの作成およびそれらへの参加、タブ、ボットの追加と構成、およびチャットや通話を行うことができます。ただし、ユーザー プロファイルの写真を変更したり、会議を作成して表示したり、コネクタを追加して構成したりすることはできません。別のユーザーが構成したコネクタからメッセージを受信することができます。

次の表では、さまざまな環境でホストされた Exchange Online のユーザーのための情報を示します。

**サポートされるアクション:** 

| ユーザーのメールボックスのホスト先:   | チームを作成する   |チームに参加する|チャネルを作成する|会議を作成して表示する|ユーザー プロフィールの写真を変更する|コネクタを追加して構成する|タブを追加して構成する|ボットを追加して構成する|
|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|はい|はい|はい|はい|はい|はい|はい|はい|
|**Exchange Online 専用 vNext**|はい|はい|はい|はい|はい|はい|はい|はい|
|**Exchange Online 専用 – レガシー** (Azure AD との同期が必要)|はい|はい|はい|いいえ|いいえ|いいえ|はい| はい|
|**Exchange On-premises** (Azure AD との同期が必要)|はい|はい|はい|はい*|いいえ|いいえ|はい|はい|
                                                            
*\*Exchange 2016 CU3 以降でサポートされます*

追加情報:

-   Microsoft Teams はオンプレミスの SharePoint をサポートしません。

-   SharePoint Online はチームの会話でファイルを共有および保存するために必要です。

-   OneDrive for Business はプライベート チャットでファイルを共有および保存するために必要です。

-   SharePoint Online ライセンスが割り当てられていないユーザーは、Office 365 に OneDrive for Business ストレージがありません。ファイル共有はチャネル内で機能し続けますが、Office 365 に OneDrive for Business ストレージがないと、ユーザーはチャット内でファイルを共有することができません。

-   ユーザーが Microsoft Teams でチームを作成するためには、Office 365 グループの作成について有効になっている必要があります。

-   Microsoft Teams では、電子情報開示、コンテンツ検索、アーカイブ、訴訟ホールドのようなセキュリティおよびコンプライアンスの機能は Exchange Online と SharePoint Online の環境で最適に動作します。チャネルの会話の場合、メッセージは Exchange Online 内のグループ メールボックスにジャーナリングされます。これらのメッセージは電子情報開示で利用できます。SharePoint Online と OneDrive for Business (職場または学校のアカウントを使用) が組織全体とユーザーに対して有効な場合は、これらのコンプライアンス機能も Teams 内のすべてのファイルに対して利用できます。

**重要** Microsoft Teams のチャット リストに含まれている会話に参加するユーザーは、管理者がチャット会話を検索できるようにするために、Exchange Online の (クラウド ベースの) メールボックスを持つ必要があります。この理由は、チャット リストに含まれている会話がチャット参加者のクラウドベースのメールボックスに保存されるためです。チャット参加者が Exchange Online のメールボックスを持っていない場合、管理者はチャットの会話を検索したり保留にしたりすることができなくなります。たとえば、Exchange のハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは Microsoft Teams のチャット リストに含まれている会話に参加できる可能性がありますが、この場合はユーザーにクラウドベースのメールボックスがないため、それらの会話の内容を検索することや、会話を保留にすることはできません。コンテンツ検索と Microsoft Teams の詳細については、[*Microsoft Teams と Office 365 グループ*](https://support.office.com/en-us/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)をご覧ください。

**ヒント:** Azure AD Connect を使用して Azure Active Directory と同期する方法については、「[*オンプレミス ID と Azure Active Directory の統合*](https://go.microsoft.com/fwlink/?linkid=854600)」をご覧ください。
