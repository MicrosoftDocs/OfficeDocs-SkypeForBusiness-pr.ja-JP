---
title: Teams の更新プログラム
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: この記事では、Microsoft Teams デスクトップ クライアントの更新のプロセスについて説明します。
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7d296e296b2f5a20b5d7d10da6e598a989f0d71
ms.sourcegitcommit: cd4464fe9bf0f38ed4c3ca058a51bcd29578eef9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65316503"
---
# <a name="teams-update-process"></a>Teams の更新プロセス

Teams Web アプリの更新プログラムは、通常、毎月第 4 月曜日にリリースされます。

Teams デスクトップ クライアントの更新プログラムは、TAP (Technology Adoption Program) を使用した厳格な内部テストと検証の後、毎月リリースされます。 デスクトップ クライアントの更新プログラムは通常、毎月第 4 月曜日に開始され、残りの週を通じて徐々にユーザーにロールアウトされます。 緊急更新プログラムが必要な場合、Teams ではこのスケジュールをバイパスし、利用可能になり次第更新プログラムをリリースします。

デスクトップ クライアントは自動的に更新されます。Teams は、数時間ごとにバックグラウンドで更新プログラムを確認します。更新プログラムをダウンロードすると、コンピューターがアイドル状態になるまで待機してから、更新プログラムをサイレント インストールします。

ユーザーは、アプリの右上にある **[プロファイル]** アイコンの横にある **[...]** ドロップダウン メニューで **[更新を確認]** を選択して、更新プログラムを手動でダウンロードすることもできます。 更新プログラムが入手可能であれば、ダウンロードが実行されて、コンピューターがアイドル状態のときにサイレント インストールされます。

更新プログラムがダウンロードされるには、ユーザーがサインインしている必要があります。

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise の更新プログラムについて

「[Microsoft 365 Apps と同時に Microsoft Teams を展開する](/DeployOffice/teams-install)」で説明されているように、Teams のインストールは既定で、Microsoft 365 Apps for enterprise の新しいインストールと一緒に行われます。

Teams は、上記で説明した独自の更新プロセスに従います。 Teams は、Word や Excel などの他のオフィス アプリの更新プロセスには追従しません。 詳細については、「[Microsoft 365 Apps の更新プログラム チャネルの概要](/DeployOffice/overview-update-channels)」を参照してください。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Teams の自動更新の代わりに、管理者が更新プログラムを展開することはできますか?

Teams では、どんな配信メカニズムを使用してであれ、管理者が更新プログラムを展開することはできません。

## <a name="servicing-agreement"></a>サービス契約

最新のオンライン サービスとして、Teams クライアントは 2 週間ごとに自動更新されます。 Teams には最新のライフサイクル ポリシーが適用されるため、ユーザーには最新バージョンのデスクトップ クライアントを使用し続けることが期待されています。 自動更新により、ユーザーは最新の機能、パフォーマンス強化、セキュリティ、サービスの信頼性を確保することができます。

デスクトップ クライアントが最新ではなくなったタイミングを特定するため、ユーザーの現在のバージョンが 1 か月から 3 か月前のものである場合、および新しいバージョンが使用できる場合に、アプリ内アラートが表示されます。 このアプリ内のメッセージ機能により、ユーザーは最新バージョンの Teams に更新するか、必要に応じて IT 管理者に連絡してそうしてもらうように促されます。 3 か月より前の Teams デスクトップ クライアントを使用しているユーザーには、ブロック ページが表示されます。このページには、すぐに更新するか、IT 管理者に連絡するか、Teams on the web に移動するかを選択するオプションが表示されます。

政府機関向けクラウドの Teams デスクトップ クライアントについては、現在のところ、別途お知らせするまでこのサービス契約の例外です。

新しいバージョンのリリースの詳細については、[メッセージ センター](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)で確認するか、クライアントの **[ヘルプ]** > **[What’s new](新機能)** を参照してください。

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI 上の Teams の更新について

仮想デスクトップ インフラストラクチャ (VDI) 上の Teams クライアントは、VDI 以外の Teams クライアントのように自動的には更新されません。 [VDI 上に Teams をインストールする](teams-for-vdi.md)ための手順に従って、新しい MSI をインストールして、VM イメージを更新する必要があります。 新しいバージョンに更新するには、現在のバージョンをアンインストールする必要があります。
