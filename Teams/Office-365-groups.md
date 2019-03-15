---
title: Office 365 のグループとマイクロソフトのチーム
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
description: Office 365 グループとグループ メンバーシップがどのように Microsoft Teams と連携しているかについて説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae3a64111ae00241d88ed6ef4b02948f1c8c75a0
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641201"
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365 のグループとマイクロソフトのチーム
=====================================

> [!Tip]
> チームが Azure Active Directory (Azure AD)、Office 365 のグループ、Exchange、SharePoint およびビジネスのための OneDrive とどのように対話する方法については、次のセッションを監視する:[マイクロソフトのチームの基礎](https://aka.ms/teams-foundations)

Office 365 のグループは、Office 365 の間アプリケーションのメンバーシップ サービスです。 基本的なレベルでは、Office 365 グループは、Azure Active Directory のオブジェクトのメンバーは、疎結合、Yammer グループでは、SharePoint チーム サイトを含む関連の作業負荷を一覧で Exchange メールボックスのリソース、プランナー、電源の BI および OneNote の共有します。 追加したり、Active Directory 内の他のグループ ベースのセキュリティ オブジェクトと同じように、グループにユーザーを削除することができます。

Office 365 管理者は、Office 365 のグループを定義、メンバーの追加、および交換、共有メールボックス、SharePoint ドキュメント ライブラリ、Yammer のグループなどのように機能を活用します。 Office 365 のグループの詳細については、 [Office 365 のグループについての説明](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)を参照してください。

<a name="how-office-365-groups-work"></a>Office 365 のグループがどのように動作するか
--------------------------

バックエンドで、チームを作成する場合、Office 365 のグループと関連付けられている SharePoint ドキュメント ライブラリと、他の Office 365 のクラウド アプリケーションにつながり、OneNote のノートブックを作成します。 チームを作成する人が既存の Office 365 のパブリックまたはプライベート グループの所有者である場合、グループにチームの機能を追加して、2500 未満の人とチームに追加されたことはありません、できます。 チャットでメッセージ、ドキュメント、OneNote、およびその他のオブジェクトが存在する 1 つの既定**全般的な**チャネルが作成されます。 チャネルのドキュメント ライブラリを表示すると、チーム内のチャネルを表す**一般的な**フォルダーが表示されます。 さらに、ドキュメント ライブラリ**それは反映されません**チームとして、チャネル内では、独自のフォルダー構造を作成する場合、ここでは、それだけフロー チームから SharePoint にします。

> [!NOTE]
> 顧客からのフィードバックに基づいて、マイクロソフトのチームでチームの作成の結果として生成された新しい Office 365 のグループされなく Outlook でデフォルトで表示されます。 Outlook でこれらのグループを示すは、既存の動作を継続するお客様の場合は、Outlook の環境のグループを有効にすることができる Exchange のオンラインの PowerShell コマンドレットが提供されます。 Outlook で作成し、後で有効になっているチームのグループは、Outlook とチームの両方に表示する続けます。 この更新プログラムを段階的には数か月の後で Outlook とチーム全体がロールバックされます。

> [!NOTE]
> Office 365 グループを削除するが Outlook と OWA の永続的な会話とチームの会議のエイリアスのメールボックスへの招待、削除とマーク、SharePoint サイトを削除。 チームを削除し、Outlook では、効果との間に約 20 分を要する。 チーム チーム クライアントから削除されますすぐにビューからすべてのチームのメンバーであります。 持つチーム機能を利用して Office 365 のグループのメンバーを削除する場合は、チームが削除された影響を受ける人のチームのクライアントのビューから削除される前に、約 2 時間の遅延が可能性があります。
>
>[この](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)削除した Office 365 のグループを復元する方法についてお読みください。

<a name="group-membership"></a>グループ メンバーシップ
----------------

グループの機能と、ユーザーのための機能は、グループのメンバーシップからのドライブの場所によって異なります。 たとえば、チームのメンバーを削除する場合は同様に、Office 365 グループから削除されます。 グループからの削除は、すぐにチームを削除し、チームのクライアントからのチャネルします。 Office 365 管理センターを使用してグループからユーザーを削除する場合に、他の共同作業の側面へのアクセスなど、SharePoint Online のドキュメント ライブラリでは、グループ、または共有の OneNote を Yammer。 ただし、それらがまだチームのチャット機能へのアクセスは約 2 時間の。

チーム メンバーを管理するためのベスト プラクティスとして追加し、他の依存するクラウド アプリケーションを正しいカスケード アクセス制御を適用することを確認するのにはチームのクライアントからメンバーを削除します。 さらに、切り離された経験したままの人まで次の同期サイクルは、追加、またはサービスの特定のコンポーネントへのアクセス権を取り消します) するために使用するリソースへのアクセスがまだあるという印象を回避します。 かどうかを追加または削除を行うチームのクライアント以外のチーム メンバー (、Azure AD は、Office 365 管理センターを使用してまたは Exchange のオンライン PowerShell)、変更をチームに反映させるには、最大で 2 時間がかかることができます。
