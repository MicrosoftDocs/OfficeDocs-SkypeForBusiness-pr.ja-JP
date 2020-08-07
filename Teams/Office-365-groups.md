---
title: Microsoft 365 グループおよび Microsoft Teams
ms.reviewer: Kyle Blevins
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
description: この記事では、microsoft 365 のグループとグループメンバーシップが Microsoft Teams とどのように連携するかについて説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a44adb84cb6669bb96bd617fb52ea9b5fdceb7af
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581128"
---
<a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 グループおよび Microsoft Teams
=====================================

> [!Tip]
> チームと Azure Active Directory (Azure AD)、Microsoft 365 グループ、Exchange、SharePoint、および OneDrive for Business がどのように連携するかについては、次のセッションをご覧ください。 [Microsoft Teams の基礎](https://aka.ms/teams-foundations)

Microsoft 365 Groups は、Office 365 のクロスアプリケーションメンバーシップサービスです。 基本的なレベルでは、Microsoft 365 グループは Azure Active Directory 内のオブジェクトであり、メンバーの一覧と、SharePoint チームサイト、Yammer グループ、共有 Exchange メールボックスリソース、Planner、Power BI、OneNote などの関連ワークロードへの疎結合が含まれています。 Active Directory の他のグループベースのセキュリティオブジェクトと同様に、グループにユーザーを追加または削除することができます。

Office 365 管理者は、Microsoft 365 グループを定義し、メンバーを追加し、Exchange 共有メールボックス、SharePoint ドキュメントライブラリ、Yammer グループなどの機能を活用することができます。 Microsoft 365 グループの詳細については、「 [microsoft 365 グループについ](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)て」を参照してください。

[IT アーキテクト向けの Microsoft 365](teams-architecture-solutions-posters.md#groups-in-microsoft-365)のポスターグループを見逃してはなりません。

<a name="how-microsoft-365-groups-work"></a>Microsoft 365 グループのしくみ
--------------------------

チームを作成する場合は、バックエンドで、Microsoft 365 グループと、関連付けられた SharePoint ドキュメントライブラリと OneNote ノートブックを、他の Office 365 クラウドアプリケーションとの連携と共に作成しています。 チームを作成しているユーザーが既存の Office 365 パブリックまたはプライベートグループの所有者である場合は、チームの機能をグループに追加することができます。これは、ユーザーが5000人未満であり、チームに追加されていない場合です。 これにより、チャットメッセージ、ドキュメント、OneNote、その他のオブジェクトが存在する既定の**全般**チャネルが1つ作成されます。 チャネルのドキュメントライブラリを表示すると、チーム内のチャネルを表す **[全般**] フォルダーが表示されます。 さらに重要なのは、ドキュメントライブラリ内に独自のフォルダー構造を作成した場合、そのファイルはチャネルとしてチームに**伝達されません**。現時点では、チームから SharePoint へのフローのみが行われます。

> [!NOTE]
> 顧客のフィードバックに基づき、Microsoft Teams クライアントでチームを作成した結果として生成された新しい Microsoft 365 グループは、既定では Outlook に表示されなくなります。 Outlook でグループの表示をオンまたはオフにするには、 **HiddenFromExchangeClientsEnabled**パラメーターを指定して[get-unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup)コマンドレットを使用します。 Outlook を使用して作成されたグループで、後で Teams を有効にした場合は、Outlook と Teams の両方に表示されたままになります。 

> [!NOTE]
> Microsoft 365 グループを削除すると、永続的な Outlook/OWA の会話と Teams の会議出席依頼のメールボックスのエイリアスが削除され、SharePoint サイトの削除のマークが付けられます。 チームの削除と Outlook への影響の間は、約20分かかります。 チームクライアントからチームを削除すると、チームのメンバーになっているすべてのユーザーに直ちにチームが削除されます。 チーム機能が有効になっている Microsoft 365 グループのメンバーを削除した場合は、削除された対象ユーザーのチームクライアントでチームがビューから削除されるまでに約2時間かかることがあります。
>
>削除した Microsoft 365 グループの復元につい[ては、こちらを](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)参照してください。

<a name="group-membership"></a>グループ メンバーシップ
----------------

ユーザーのグループの機能と機能は、グループメンバーシップの場所によって異なります。 たとえば、チームのメンバーを削除すると、Microsoft 365 グループからも削除されます。 グループから削除すると、チームクライアントからチームとチャネルが直ちに削除されます。 Microsoft 365 管理センターを使用してグループからユーザーを削除すると、SharePoint Online ドキュメントライブラリ、Yammer グループ、共有 OneNote などの他の共同作業の側面にはアクセスできなくなります。 ただし、チームのチャット機能へのアクセス権は、約2時間で引き続き利用できます。

チームメンバーを管理するためのベストプラクティスとして、チームクライアントからメンバーを追加または削除して、他の依存クラウドアプリケーションへの適切な連鎖アクセス制御が適用されていることを確認します。 さらに、分離された環境では、ユーザーが使用したリソースに引き続きアクセスできるという印象を与えないようにします (次の同期サイクルで、サービスの特定のコンポーネントへのアクセスが追加または取り消されるまで)。 Teams クライアントの外部でチームメンバーを追加または削除する場合 (Microsoft 365 管理センター、Azure AD、または Exchange Online PowerShell を使用して)、変更が Teams に反映されるまでに最大で24時間かかる場合があります。

<a name="ability-to-add-group-as-attendee-while-scheduling-meetings"></a>会議のスケジュールを設定しているときにグループを出席者として追加する機能
----------------------------------------------------------

2020年5月以降、グループをスケジュールされた会議に招待できるようになりました。次の点にご注意ください。
1. 既存の Microsoft 365 グループから作成された既存の Microsoft 365 グループとチームはすべて検索可能になり、会議に追加することができます。 ただし、メンバーは、グループのサブスクリプションに基づいて会議出席依頼を受信します。
2. 最初から作成されたチームは、2018でも検索可能になりますが、既定のグループのサブスクリプションによって会議の出席依頼が受信されることはありません。 "自分に返信する" というメッセージが表示されます。 グループの設定を変更することで、Outlook から変更することができます。
3. 2018年5月以降に最初から作成された Teams は検索可能ではないため、"HiddenFromAddressListsEnabled" プロパティを使って非表示になります。 これは管理者によって管理される設定であり、管理者が変更することができます。
