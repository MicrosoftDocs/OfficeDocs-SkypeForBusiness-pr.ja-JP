---
title: Microsoft 365 管理センターを使用してリソースアカウントを作成する
description: グラフィカルユーザーインターフェイスを使用する場合は、microsoft 365 管理センターを使用して、microsoft teams の会議室とコラボレーションバーのリソースアカウントを作成することができます。
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: デバイスアカウントの作成、Microsoft 365 UI、Microsoft 365 管理センター
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1137f462b9c21455f3a65a87075fd653b5c081b9
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268037"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターを使用して Microsoft 365 リソースアカウントを作成する

Microsoft 365 リソースアカウントは、会議室、プロジェクターなどの特定のリソース専用のメールボックスおよび Teams アカウントです。 これらのリソースアカウントは、作成時に定義したルールを使って、会議出席依頼に自動的に応答できます。 たとえば、会議室などの共通のリソースがある場合は、その会議室のリソースアカウントを設定して、会議の出席依頼を自動的に承諾または拒否することができます。

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>ライセンス

Microsoft 365 リソースアカウントを作成する前に、必要なライセンスの種類を確認してください。 リソースアカウントを使用してリソースを予約する場合 (つまり、会議にリソースを招待し、招待を自動的に承諾または辞退した場合)、リソースアカウントにライセンスを割り当てる必要はありません。 次のような場合は、リソースアカウントにライセンスを割り当てる必要があります。

- **Teams 会議** リソース (Microsoft Teams のルーム本体、コラボレーションバーなど) を Teams 会議に参加させて、参加者がビデオや音声を使ってビデオや音声を表示できるようにするには、会議室のライセンスが必要です。 
- **PSTN 通話** リソースが外部電話番号 (公衆交換電話網または PSTN 通話と呼ばれます) に対して通話を発信または受信できるようにするには、Microsoft 365 電話システムまたは Microsoft 365 Business Voice license が必要です。

会議室、電話システム、ビジネス用ボイスライセンスの詳細については、「 [Microsoft Teams のアドオンライセンス](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Microsoft 365 管理センターでリソースアカウントを作成する

1. アクセスして、Microsoft 365 にサインインします。 https://admin.microsoft.com
2. Microsoft 365 テナントの管理者資格情報を入力します。 この操作を行うと、Microsoft 365 管理センターに移動します。

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 管理センター":::
3. 管理センターで、左側のパネルの [ **リソース** ] に移動し ([ **すべて表示** ] を選択します)、[ **会議室] & [備品**] を選択します。

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365 管理センター-リソース":::
4. [ **リソースメールボックスの追加** ] を選択して、新しい会議室アカウントを作成します。 アカウントの表示名とメールアドレスを入力し、[ **追加**]、[ **閉じる**] の順に選択します。 すべてのリソースアカウントの命名規則を標準化することをお勧めします。

> [!NOTE]
> 既定では、リソースアカウントは次の設定で設定されます。 設定を変更する場合は、[**閉じる**] を選択する前に、[**スケジュールオプションの設定**] を選択します。 後で変更する場合は、[**リソース**  >  **ルーム & 備品**] に移動してリソースアカウントを選択し、[**予約オプション**] の [**編集**] を選択します。
>
> - 会議の繰り返しを許可する
> - 次の制限を超えて会議を自動的に辞退する
>   - 予約ウィンドウ (日数): 180
>   - 最大期間 (時間):24
> - 会議出席依頼を自動承諾する

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 管理センター-リソースを追加する":::
5. 管理センターの [ **ユーザー** ] セクションに移動し、[ **アクティブなユーザー** ] の一覧に、作成した会議室が表示されます。

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 管理センター-アクティブなユーザーを表示する":::
6. 会議室の名前を選択すると、アカウントのプロパティパネルが右側に表示されます。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 管理センター-ユーザープロパティ":::
7. 次に、リソースアカウントにパスワードを割り当てる必要があります。 パネルでは、アカウントのプロパティといくつかのオプションの操作を確認できます。 [パスワードを変更するには、ユーザー名] の下にあるパスワードキーの **リセット** アイコンを選択します。 **[ユーザーが最初にサインインしたときに、このユーザーにパスワードの変更を要求する**(オフ)。 デバイスのサインイン処理を使用してパスワードを変更することはできません。 [ **リセット**] を選びます。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 管理センター-パスワードの再設定":::
8. [ **ライセンスとアプリ** ] セクションで、デバイスのインストール先の国または地域を **[場所]** に設定します。 下にスクロールし、会議室など、割り当てるライセンスの隣にあるチェックボックスをオンにして、[ **変更の保存**] を選択します。 ライセンスは、組織によって異なる場合があります。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 管理センター-ライセンスの割り当て":::
