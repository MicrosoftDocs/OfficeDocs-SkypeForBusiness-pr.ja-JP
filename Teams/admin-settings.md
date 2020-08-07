---
title: Microsoft Teams でのアプリの管理設定
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Microsoft Teams で組織のアプリの管理に使用できるポリシーと設定について説明します。
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
f1.keywords:
- CSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6235352b845898c194e82f3ec292539904a7f61c
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582444"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Microsoft Teams でのアプリの管理設定
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

アプリは、組織が Teams を活用できるよう最先端のツールを提供しています。 このアプリは、Microsoft が提供する、サードパーティがまたは組織の開発者が開発したタブ、メッセージング拡張機能、コネクタ、ボットの機能を組み合わせたものです。

管理センターの**Teams アプリ**で組織のアプリを管理します。 (「[チーム管理者ロールを使用](https://docs.microsoft.com/microsoftteams/using-admin-roles)してチームを管理し、管理者ロールと権限を取得する」を参照してください。)たとえば、組織レベルでアプリを許可またはブロックしたり、チームユーザーが利用できるアプリを制御するポリシーを設定したり、ユーザーにとって最も重要なアプリを固定することで、チームをカスタマイズしたりすることができます。

Microsoft では、Teams でのアプリ エクスペリエンスの継続的な改善と、機能の追加を行うための取り組みを行っています。 後日、アプリの管理機能が追加されますので、アプリ ポリシーの最新情報をご確認ください。

## <a name="manage-apps"></a>アプリを管理する

**[アプリの管理]** ページを使用して、組織のアプリ カタログにあるすべての Teams アプリを表示および管理できます。 アプリの組織レベルでの状態とプロパティの確認、組織レベルでのアプリのブロックまたは許可、テナント カタログへの新しいカスタム アプリのアップロード、組織全体のアプリ設定の管理を行うことができます。

**[アプリの管理]** ページでは、テナント カタログ内の使用可能なすべてのアプリを確認することができます。また、組織全体で許可またはブロックするアプリを決定するために必要な情報を提供します。 また、[アプリのアクセス許可ポリシー](#app-permission-policies)、[アプリのセットアップ ポリシー](#app-setup-policies)、[カスタム アプリ ポリシーと設定](#custom-app-policies-and-settings)を使って、組織内の特定のユーザーに対してアプリ エクスペリエンスの構成を行うことができます。

詳細については、「[Teams でアプリを管理する](manage-apps.md)」を参照してください。

## <a name="app-permission-policies"></a>アプリのアクセス許可ポリシー

アプリのアクセス許可ポリシーを使用して、組織内の特定のユーザーが使用できるアプリを制御できます。 すべてのアプリ、または Microsoft、第三者、お客様の組織によって公開されている特定のアプリを許可またはブロックすることができます。

たとえば、アプリのアクセス許可ポリシーは次のことに使用できます。

- 特定のユーザーに新しいサード パーティ製またはカスタムビルド版のアプリを徐々に展開する。
- 組織全体で Teams の展開を開始する際に、特にユーザーの作業を簡略化する。

詳細については、「[Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)」にアクセスしてください。

## <a name="app-setup-policies"></a>アプリケーションの設定ポリシー

アプリケーションの設定ポリシーで、ユーザーのアプリでの操作をカスタマイズできます。 Teams クライアントのアプリ バーに固定するアプリと、アプリが Web、デスクトップ、モバイル クライアントに表示される順序を選択します。

アプリの設定ポリシーの活用例は以下のとおりです。

- 主要アプリの認識と導入を促進する。 たとえば、人事チームのユーザー用のカスタム採用管理と人材管理アプリを固定します。
- チャット、Teams、通話などの主要な Teams 機能を選択して固定します。 これを行うと、ユーザーが確実に Teams 内の特定のアクティビティに取り組めるようになります。

詳細については、「[Teams でアプリの設定ポリシーを管理する](teams-app-setup-policies.md)」を確認してください。

## <a name="custom-app-policies-and-settings"></a>カスタム アプリ ポリシーと設定

Teams により、組織の開発者がその他のユーザーにカスタム アプリを構築、テスト、展開できるようにします。 カスタム パッケージは、.zip ファイルのアプリ パッケージをチームに直接アップロードするか、個人のコンテキストにアップロードして、チームに追加できます。 組織でカスタム アプリをアップロードできる人物を管理するアプリの設定ポリシーを使用できます。 ユーザーが特定のカスタム アプリを操作するかどうかを制御する組織全体の設定を設定することもできます。

詳細については、「[Teams のカスタム アプリのポリシーと設定を管理する](teams-custom-app-policies-and-settings.md)」にアクセスしてください。
