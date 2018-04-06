---
title: Office 365 グループと Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Office 365 グループとグループ メンバーシップがどのように Microsoft Teams と連携しているかについて説明します。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f16a99f00add1e93bfdf4cde29f4b75f384a296
ms.sourcegitcommit: cacd16f596460c1400dd514437794afd04bddadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2018
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365 グループと Microsoft Teams
=====================================

Office 365 グループは Office 365 のクロスアプリケーションのメンバーシップ サービスです。基本的なレベルでは、Office 365 グループはメンバーのリストを含む Azure Active Directory のオブジェクトです。さらに、このオブジェクトには SharePoint チーム サイト、Yammer グループ、Exchange メールボックスのリソース、Planner、PowerBI、OneNote などの関連ワークロードとの疎結合も含まれています。Active Directory のその他のグループベースのセキュリティ オブジェクトと同様にグループにユーザーを追加したり、グループからユーザーを削除することができます。

Office 365 の管理者は Office 365 グループの定義やメンバーの追加を行うことができ、Exchange 共有メールボックス、SharePoint ドキュメント ライブラリなどの機能も利用することができます。グループについて詳しくは、「[Office 365 グループの概要](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)」をご覧ください。

<a name="how-office-365-groups-work"></a>Office 365 グループについて
--------------------------

Microsoft Teams のチームを作成することは、最終的には SharePoint ドキュメント ライブラリ、OneNote ノートブック、その他の Office 365 クラウド アプリケーションと関連付けられた Office 365 グループを作成することを意味します。チームを作成しているユーザーが既存の Office 365 パブリックまたはプライベート グループの所有者である場合は、Teams の機能をグループに追加できます。追加を行うと、チャット メッセージ、ドキュメント、OneNote、その他のオブジェクトが配置される既定の「全般」チャネルが作成されます。そのチャネルのドキュメント ライブラリを表示すると、チームのチャネルを表す「全般」フォルダーが表示されます。さらに重要な点は、ドキュメント ライブラリ内で独自のフォルダー構造を作成しても、それはチャネルとして Teams に**伝播されません**。現時点では、Teams から SharePoint にのみ伝播されます。




> [!NOTE]
> Office 365 グループを削除すると、永続的な Outlook/OWA の会話や Teams 会議への招待状のメールボックス エイリアスが削除され、SharePoint サイトに削除のマークが付けられます。チームを削除した時点からそれが Outlook に反映されるまでに約 20 分かかります。Teams クライアントからチームを削除すると、そのチームのすべてのメンバーの表示からそのチームが即座に削除されます。Teams の機能を有効にしている Office 365 グループからメンバーを削除すると、削除したメンバーの Teams クライアントの表示からそのチームが削除されるまでに約 1 時間の遅延が発生します。

<a name="group-membership"></a>グループ メンバーシップ
----------------

グループの機能と、ユーザーのための機能は、グループのメンバーシップからのドライブの場所によって異なります。 たとえば、チームのメンバーを削除する場合は同様に、Office 365 グループから削除されます。 グループからの削除は、すぐにチームを削除し、チームのクライアントからのチャネルします。 Office 365 管理ポータルを使用してグループからユーザーを削除する場合は、他の共同作業の側面へのアクセス、Yammer グループ、または共有の OneNote の SharePoint Online のドキュメント ライブラリなど。 ただし、それらがまだチームのチャット機能へのアクセスを約 1 時間です。

チーム メンバーを管理するためのベストプラクティス: を追加し、他の依存するクラウド アプリケーションを正しいカスケード アクセス制御が適用されることを確認するのにはチームのクライアントからメンバーを削除します。 さらに、切り離された経験したままの人まで次の同期サイクルは、追加、またはサービスの特定のコンポーネントへのアクセス権を取り消します) するために使用するリソースへのアクセスがまだあるという印象を回避します。 かどうかを追加または削除を行うチームのクライアント以外のチーム メンバー (Office 365 の管理者センター、Azure AD を使用して、または Exchange のオンライン PowerShell)、チームに反映させるには、最大で 1 時間がかかる場合があります。
