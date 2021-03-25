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
description: この記事では、Microsoft Teams デスクトップ クライアントを更新するプロセスについて説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68e26325f4efcc5ffd7731b73e397f1f96579dd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119246"
---
# <a name="teams-update-process"></a>Teams の更新プロセス

Teams Web アプリは毎週更新されます。

Teams デスクトップ クライアントの更新プログラムは、TAP (Technology Adoption Program) を使用した厳格な内部テストと検証の後、2 週間ごとにリリースされます。 更新プログラムは通常、火曜日に行います。 緊急更新プログラムが必要な場合、Teams ではこのスケジュールをバイパスし、利用可能になり次第更新プログラムをリリースします。

デスクトップ クライアントは自動的に更新されます。 Teams は、数時間ごとにバックグラウンドで更新プログラムを確認します。更新プログラムをダウンロードすると、コンピューターがアイドル状態になるまで待機してから、更新プログラムをサイレント インストールします。

ユーザーは、アプリの上部にある [プロファイル] ドロップダウンメニューで [更新プログラムの確認] を選択して、更新プログラムを手動でダウンロードすることもできます。 更新プログラムが入手可能であれば、ダウンロードが実行されて、コンピューターがアイドル状態のときにサイレント インストールされます。

更新プログラムがダウンロードされるには、ユーザーがサインインしている必要があります。

2019 年 7 月 31 日から、Teams クライアントの更新プログラムでは、更新時に使用されるネットワーク帯域幅が低くなります。 この更新プログラムは既定で有効になっているので、管理者やユーザーからの操作は必要はありません。

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise の更新プログラムについて

「[Microsoft 365 Apps と同時に Microsoft Teams を展開する](/DeployOffice/teams-install)」で説明されているように、Teams のインストールは既定で、Microsoft 365 Apps for enterprise の新しいインストールと一緒に行われます。

Teams は、上記で説明した独自の更新プロセスに従います。 Teams は、Word や Excel などの他のオフィス アプリの更新プロセスに従わない。 詳細については、「[Microsoft 365 Apps for enterprise の更新プログラム チャネルの概要](/DeployOffice/overview-of-update-channels-for-office-365-proplus)」を参照してください

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI 上の Teams の更新について


仮想デスクトップ インフラストラクチャ (VDI) 上の Teams クライアントは、VDI 以外の Teams クライアントのように自動的には更新されません。 [VDI 上に Teams をインストールする](teams-for-vdi.md)ための手順に従って、新しい MSI をインストールして、VM イメージを更新する必要があります。 新しいバージョンに更新するには、現在のバージョンをアンインストールする必要があります。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Teams の自動更新の代わりに、管理者が更新プログラムを展開することはできますか?

Teams では、管理者は配信メカニズムを通じて更新プログラムを展開する機能を提供しない。

## <a name="servicing-agreement"></a>サービス契約

最新のオンライン サービスとして、Teams クライアントは 2 週間ごとに自動更新されます。 Teams には最新のライフサイクル ポリシーが適用されるため、ユーザーには最新バージョンのデスクトップ クライアントを使用し続けることが期待されています。 自動更新により、ユーザーは最新の機能、パフォーマンスの強化、セキュリティ、およびサービスの信頼性を確保できます。

デスクトップ クライアントが古い日付を特定するために、ユーザーの現在のバージョンが 1 か月から 3 か月後の場合、および利用可能な新しいバージョンがある場合は、アプリ内通知が表示されます。 このアプリ内のメッセージ機能により、ユーザーは最新バージョンの Teams に更新するか、必要に応じて IT 管理者に連絡してそうしてもらうように促されます。 3 か月より前の Teams デスクトップ クライアントを使用しているユーザーには、ブロック ページが表示されます。このページには、すぐに更新するか、IT 管理者に連絡するか、Teams on the web に移動するかを選択するオプションが表示されます。

デスクトップ クライアント バージョンが、最初のインストールまたは Teams を初めて実行した時点で 3 か月より前のものである場合は、上述のサービス情報が表示されるまで 28 日間の猶予期間が設定されています。 この期間中に、自動更新プロセスによって Teams クライアントが更新されます。 更新されていない場合は、最新バージョンの Teams に手動で更新するアプリ内通知が表示されます。 ユーザーは、更新を行う IT 管理者に問い合わせするように求めされる場合があります。 対象となるのは、Teams デスクトップ クライアントを Microsoft 365 Apps for enterprise バンドルの一部として使用しているユーザーです。

政府機関向けクラウドの Teams デスクトップ クライアントについては、現在のところ、別途お知らせするまでこのサービス契約の例外です。

新しいバージョンのリリースの詳細については、[メッセージ センター](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)で確認するか、クライアントの **[ヘルプ]** > **[What’s new](新機能)** を参照してください。
