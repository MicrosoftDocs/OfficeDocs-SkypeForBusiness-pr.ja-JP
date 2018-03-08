---
title: "Exchange や Microsoft チームを操作する方法"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft チームとの作成や、チーム、チャネルを作成するへの参加などのさまざまな Exchange 設定が存在する機能について説明します。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 4fc7da7d68c13bbadec935573c827cf767c9afe4
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Exchange や Microsoft チームを操作する方法 
=========================================

完全な Microsoft チーム操作には、SharePoint Online、Exchange Online および Office 365 のグループの作成のすべてのユーザーを有効にする必要があります。

ユーザーの Exchange メールボックスがホストされているオンラインまたは内部設置型します。Exchange Online または Exchange 専用 vNext でホストされているユーザーには、チームのすべての機能を使用できます。ことができますを作成してチームとチャンネルに参加するを作成して会議を表示、およびチャット、ユーザー プロファイルの写真を変更、追加をコネクタ、タブ、およびコンポーネントを構成するクリックします。

ユーザーが内部設置型か Exchange オンライン専用 - レガシ、または Exchange でホストされている、Office 365 の Azure Active Directory に同期する必要があります。作成、チームとチャンネルに参加する、追加、タブとコンポーネントを構成することができますが、チャットし、通話できます。ただし、ユーザー プロファイルの写真を変更または追加してコネクタを構成する、ことはできません。他のユーザーが構成されているコネクタからメッセージを受信することができます。混在を袋、作成し、会議を表示する場合: for Exchange 2016 累積的な更新プログラム (CU3) を 3 と上ではなく Exchange 2016 CU3 よりも前のバージョンを作成して、会議の表示がサポートされています。

次の表は、Exchange online のさまざまな環境でホストされているユーザー向けの情報を提供します。

**サポートされる動作:** 

| ユーザーのメールボックスがでホストされています。   | チームを作成します。   |チームへの参加します。|チャンネルを作成します。|作成して会議を表示します。|ユーザー プロファイルの画像を変更します。|追加し、コネクタの構成|追加してタブを構成します。|追加し、ロボットを構成します。|
|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|○|○|○|○|○|○|○|○|
|**Exchange Online 専用 vNext**|○|○|○|○|○|○|○|○|
|**Exchange Online 専用-レガシ**(と同期するために必要な Azure AD)|○|○|○|×|×|×|○| ○|
|**Exchange が社内**(と同期するために必要な Azure AD)|○|○|○|○*|×|×|○|○|
                                                            
*\*2016 CU3 を交換し、上にあるサポート*

追加情報:

-   Microsoft チームは、社内 SharePoint をサポートしていません。

-   共有し、チームでの会話にファイルを保存する SharePoint Online が必要です。

-   OneDrive for Business を共有して、秘密チャットにファイルを保存する必要があります。

-   ユーザーは、割り当てられているし、SharePoint Online のライセンスで有効になっていない] の場合は、OneDrive for Business の容量を Office 365 でがありません。チャネルでの作業を続けられますがファイルの共有は、ユーザーは、Office 365 でビジネスの記憶域のチャット OneDrive せずにファイルを共有できません。

-   Microsoft チームでチームを作成するのにはグループの作成を Office 365 にユーザーを有効にする必要があります。

-   Microsoft チーム、セキュリティ、コンプライアンスの機能に電子情報開示、コンテンツの検索、アーカイブ、および法的保留中の作業のように最適な Exchange Online と SharePoint Online 環境。チャンネルの会話のためのメッセージは、Exchange Online、電子情報開示で利用できる、そこからのグループ メールボックスに履歴。SharePoint Online と OneDrive for Business (作業時間または学校のアカウント) には、組織全体で、ユーザーが有効な場合は、これらの法令遵守の機能をチーム内ですべてファイルも利用できます。

**重要な:**  Microsoft チームの [チャット] リストの一部の会話に参加するユーザーには、チャットの会話を検索するには、管理者の Exchange Online (クラウド ベース) のメールボックスが必要です。チャットのリストの一部の会話、チャット参加者のクラウド ベースのメールボックスに格納されているためにです。チャットの参加者には、Exchange Online メールボックスが割り当てられていない、管理者チャットの会話を保留を配置または検索することはできません。たとえば、Exchange ハイブリッド展開では、オンプレミスのメールボックスを持つユーザーあります Microsoft チームの [チャット] ボックスの一覧に含まれる会話に参加すること。ただし、この例では、これらの会話からコンテンツ検索できないし、ユーザーは、クラウド ベースのメールボックスを持っていないために、保留に配置することはできません。コンテンツの検索や Microsoft チームの詳細については、 [*Microsoft チームと Office 365 グループ*](https://support.office.com/en-us/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)を参照してください。

**ヒント:**  Azure AD 接続を使って Azure Active Directory と同期する方法については、[*オンプレミス ユーザーの Azure Active Directory を統合する*](https://go.microsoft.com/fwlink/?linkid=854600)を参照してください。
