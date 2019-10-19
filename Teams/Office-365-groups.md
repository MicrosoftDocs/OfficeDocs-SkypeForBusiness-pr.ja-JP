---
title: Office 365 グループおよび Microsoft Teams
ms.reviewer: phlouie
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
description: Office 365 グループとグループ メンバーシップがどのように Microsoft Teams と連携しているかについて説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fff9b4165770afa61c6f89fb83088a37b221f677
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "37563864"
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365 グループおよび Microsoft Teams
=====================================

> [!Tip]
> チームと Azure Active Directory (Azure AD)、Office 365 グループ、Exchange、SharePoint、および OneDrive for Business がどのように連携するかについては、次のセッションをご覧ください。 [Microsoft Teams の基礎](https://aka.ms/teams-foundations)

Office 365 グループは、Office 365 のアプリケーション間のメンバーシップサービスです。 基本的なレベルでは、Office 365 グループは Azure Active Directory 内のオブジェクトであり、メンバーの一覧と、SharePoint チームサイト、Yammer グループ、共有 Exchange メールボックスリソース、Planner、Power BI、OneNote などの関連ワークロードへの疎結合が含まれています。 Active Directory の他のグループベースのセキュリティオブジェクトと同様に、グループにユーザーを追加または削除することができます。

Office 365 管理者は、Exchange 共有メールボックス、SharePoint ドキュメントライブラリ、Yammer グループなどの機能を使用して、Office 365 グループの定義、メンバーの追加、利点を得ることができます。 Office 365 グループの詳細については、「 [office 365 グループについ](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)て」を参照してください。

[IT アーキテクト向けの Microsoft 365](teams-architecture-solutions-posters.md#groups-in-microsoft-365)のポスターグループを見逃してはなりません。

<a name="how-office-365-groups-work"></a>Office 365 グループのしくみ
--------------------------

チームを作成する際には、バックエンドで、Office 365 グループと、関連付けられた SharePoint ドキュメントライブラリと OneNote ノートブックを、他の Office 365 クラウドアプリケーションとの連携と共に作成しています。 チームを作成しているユーザーが既存の Office 365 パブリックまたはプライベートグループの所有者である場合は、チームの機能をグループに追加することができます。これは、ユーザーが5000人未満であり、チームに追加されていない場合です。 これにより、チャットメッセージ、ドキュメント、OneNote、その他のオブジェクトが存在する既定の**全般**チャネルが1つ作成されます。 チャネルのドキュメントライブラリを表示すると、チーム内のチャネルを表す **[全般**] フォルダーが表示されます。 さらに重要なのは、ドキュメントライブラリ内に独自のフォルダー構造を作成した場合、そのファイルはチャネルとしてチームに**伝達されません**。現時点では、チームから SharePoint へのフローのみが行われます。

> [!NOTE]
> 顧客のフィードバックに基づき、Microsoft Teams でチームを作成した結果として生成された新しい Office 365 グループは、既定では Outlook に表示されなくなります。 Outlook でこれらのグループを表示する既存の動作を継続する場合は、Exchange Online PowerShell コマンドレットが提供されます。これにより、Outlook のエクスペリエンスにグループを有効にすることができます。 Outlook を使用して作成されたグループで、後で Teams を有効にした場合は、Outlook と Teams の両方に表示されたままになります。 この更新プログラムは、数か月以内に Outlook と Teams の間で段階的にロールアウトされます。

> [!NOTE]
> Office 365 グループを削除すると、永続的な Outlook/OWA の会話と Teams の会議出席依頼のメールボックスエイリアスが削除され、SharePoint サイトの削除のマークが付けられます。 チームの削除と Outlook への影響の間は、約20分かかります。 チームクライアントからチームを削除すると、チームのメンバーになっているすべてのユーザーに直ちにチームが削除されます。 チーム機能が有効になっている Office 365 グループのメンバーを削除した場合、削除された影響を受けるユーザーのチームクライアントでチームがビューから削除されるまでに約2時間かかることがあります。
>
>削除した Office 365 グループの復元につい[ては、こちらを](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)参照してください。

<a name="group-membership"></a>グループ メンバーシップ
----------------

ユーザーのグループの機能と機能は、グループメンバーシップの場所によって異なります。 たとえば、チームのメンバーを削除すると、Office 365 グループからも削除されます。 グループから削除すると、チームクライアントからチームとチャネルが直ちに削除されます。 Microsoft 365 管理センターを使用してグループからユーザーを削除すると、SharePoint Online ドキュメントライブラリ、Yammer グループ、共有 OneNote などの他の共同作業の側面にはアクセスできなくなります。 ただし、チームのチャット機能へのアクセス権は、約2時間で引き続き利用できます。

チームメンバーを管理するためのベストプラクティスとして、チームクライアントからメンバーを追加または削除して、他の依存クラウドアプリケーションへの適切な連鎖アクセス制御が適用されていることを確認します。 さらに、分離された環境では、ユーザーが使用したリソースに引き続きアクセスできるという印象を与えないようにします (次の同期サイクルで、サービスの特定のコンポーネントへのアクセスが追加または取り消されるまで)。 Teams クライアントの外部でチームメンバーを追加または削除する場合 (Microsoft 365 管理センター、Azure AD、または Exchange Online PowerShell を使用して)、変更が Teams に反映されるまでに最大2時間かかることがあります。
