---
title: 次のコマンドを使用してリソース アカウントをMicrosoft 365 管理センター
description: グラフィカル ユーザー インターフェイスを使用する場合は、Microsoft Teams センターを使用して、Microsoft Teams 会議室とコラボレーション バーのリソース アカウントMicrosoft Teams作成Microsoft 365 管理できます。
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: デバイス アカウントの作成、UI Microsoft 365作成、Microsoft 365 管理センター
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 5107521b6b3c3cb69ccb33df1a895edc5fe8b7d9
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732016"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>リソース アカウントをMicrosoft 365してリソース アカウントを作成Microsoft 365 管理センター

Microsoft 365アカウントは、会議室Teamsプロジェクターなど、特定のリソース専用のメールボックス アカウントとリソース アカウントです。 これらのリソース アカウントは、作成時に定義したルールを使用して、会議出席招待に自動的に応答できます。 たとえば、会議室などの一般的なリソースがある場合は、予定表の空き時間に応じて会議出席招待を自動的に承諾または拒否する、その会議室のリソース アカウントを設定できます。

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>ライセンス

リソース アカウントを作成Microsoft 365、必要なライセンスの種類を確認してください。 リソース アカウントを使用してリソースを予約する場合 (つまり、リソースを会議に招待し、招待を自動的に承諾または拒否する) 場合は、リソース アカウントにライセンスを割り当てる必要があります。 次の状況では、リソース アカウントにライセンスを割り当てる必要があります。

- **Teams会議** リソース (Microsoft Teams 会議室コンソール、コラボレーション バーなど) を Teams 会議に参加して、出席者がそれを使用してビデオやオーディオを表示するには、ミーティング ルーム ライセンスが必要です。 
- **PSTN 通話** リソースが外部の電話番号 (公衆交換電話網または PSTN 通話と呼ばれる) との間で通話を発信または受信するには、Microsoft 365 電話システム または Microsoft 365 Business Voice ライセンスが必要です。

ミーティング ルーム、電話システム、Business Voice のライセンスの詳細については、「Microsoft Teams アドオン ライセンス[」を参照してください。](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>リソース アカウントを作成するMicrosoft 365 管理センター

1. にアクセスしてMicrosoft 365にサインインします。https://admin.microsoft.com
2. テナントの管理者資格情報をMicrosoft 365します。 これにより、自分のアカウントにMicrosoft 365 管理センター。

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 管理センター。":::
3. 管理センターで、左側のパネルで [**リソース**] に移動し (最初に [すべて表示] を選択する必要がある場合があります)、[会議室] を選択&**します**。

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365 管理センター - リソース。":::
4. [ **リソース メールボックスの追加] を選択** して、新しいルーム アカウントを作成します。 アカウントの表示名とメール アドレスを入力し、[追加] を選択して、[閉じる] を **選択します**。 すべてのリソース アカウントの名前付け規則を標準化することをお勧めします。

> [!NOTE]
> 既定では、リソース アカウントは次の設定で設定されます。 それらを変更する場合は、[閉じる] を選択 **する前** に [スケジュール オプションの設定] を **選択します**。 後で変更する場合は、[リソース ルーム] &機器] に移動し、リソース アカウントを選択し、[予約オプション] の [編集]  >  **を選択します**。 
>
> - 繰り返し会議を許可する
> - 次の制限を超え、会議を自動的に拒否する
>   - 予約期間 (日): 180
>   - 最大期間 (時間): 24
> - 会議出席依頼を自動承諾する

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 管理センター - リソースの追加。":::
5. 管理センターの **[ユーザー** ] セクションに移動し、[アクティブなユーザー] の一覧に、作成したルームが表示されます。

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 管理センター - アクティブなユーザーを表示します。":::
6. ルームの名前を選択すると、アカウントのプロパティ パネルが右側に表示されます。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 管理センター - ユーザー プロパティ。":::
7. 次に、リソース アカウントにパスワードを割り当てる必要があります。 パネルには、アカウントのプロパティといくつかのオプションアクションが表示されます。 ユーザー名の **下にある** [パスワード キーのリセット] アイコンを選択して、パスワードを変更します。 [この **ユーザーが初めてサインインするときにパスワードを変更する] を選択解除します**。 デバイスのサインイン プロセスを使用してパスワードを変更することはできません。 [リセット] **を選択します**。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 管理センター - パスワードのリセット。":::
8. [ライセンス **とアプリ] セクション** で **、[場所の** 選択] をデバイスがインストールされる国または地域に設定します。 下にスクロールし、割り当てるライセンスの横にあるチェック ボックス ([ミーティング ルーム] など) をオンにし、[変更を保存]**を選択します**。 ライセンスは組織によって異なる場合があります。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 管理センター - ライセンスの割り当て。":::
