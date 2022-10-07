---
title: 手順 5 - 概要
ms.author: dstrome
author: dstrome
f1.keywords:
- Teams hybrid
- remote work
- Teams meetings
manager: serdars
audience: ITPro
description: 組織内で新しいTeams Rooms デバイスをセットアップする完全なプロセスをステップ実行します。
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
ms.collection:
- m365solution-teamshybrid
- m365solution-scenario
ms.custom: ''
keywords: ''
ms.openlocfilehash: 2255aa52ec04354799761c7785cfc5f761a1e962
ms.sourcegitcommit: 957502f999512a32794a9f99e292588d66ed8a33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2022
ms.locfileid: "67885665"
---
# <a name="step-5---overview"></a>手順 5 - 概要

:::image type="content" source="media/hybrid-audience-itpro-small.png" alt-text="IT Pro の対象ユーザー" border="false":::

すべてのデバイスをインストールして接続したら、Teams Rooms コンソールを構成します。

Teams Roomsが組織と連携するには、いくつかの手順を完了する必要があります。 次の手順では、Teams Room のアカウントとライセンスを設定し、会議出席依頼を処理する方法を説明し、会議でいつ、参加者が実行できるか、できないかを伝えます。

## <a name="before-you-begin"></a>はじめに

- 以下の手順を完了するには、グローバル管理者と Teams 管理者である必要があります。 詳細については、「 [Microsoft 365 管理者ロールについて」を](/microsoft-365/admin/add-users/about-admin-roles)参照してください。

## <a name="set-up-the-teams-room-account"></a>Teams Room アカウントを設定する

次の手順では、Teams Rooms コンソールのライセンスを購入し、そのライセンスのアカウントを作成し、そのライセンスをその本体に割り当てる方法を示します。 各 Teams Room コンソールが正常に動作するには、独自のアカウントとライセンスが必要です。 作成したアカウントは、Outlook で予約可能な会議室として組織のアドレス一覧に表示されます。

[手順 1 - Teams Rooms コンソールのライセンスを購入する](hybrid-meetings-device-config-license.md)

[手順 2 - リソース アカウントを作成する](hybrid-meetings-device-config-account.md)

[手順 3 - 会議室のライセンスを割り当てる](hybrid-meetings-device-config-assign.md)

## <a name="configure-mailbox-and-account-properties"></a>メールボックスとアカウントのプロパティを構成する

組織のユーザーが Teams ルームを予約できるようにするには、コンソールで使用するアカウントでいくつかのプロパティを構成する必要があります。 これらのプロパティを設定すると、Teams Room は会議出席依頼を目的の方法で自動的に処理したり、コンソールで会議に関する情報を削除または追加したり、会議出席依頼の応答に含める必要のある情報を設定したりできます。

コンソールがアカウントにログインできるように、Teams Rooms リソース アカウントでパスワードの有効期限をオフにする必要があります。

[手順 4 - メールボックスのプロパティを構成する](hybrid-meetings-device-config-mailbox.md)

[手順 5 - パスワードの有効期限を無効にする](hybrid-meetings-device-config-password.md)

## <a name="configure-meeting-policies-and-options"></a>会議ポリシーとオプションを構成する

会議ポリシーは、組織内のユーザーによってスケジュールされた会議への参加者が利用できる機能を制御するために使用されます。 たとえば、参加者がビデオを共有したり、匿名の参加者を許可またはブロックしたり、会議を記録できるかどうかを制御したり、それらの記録の保存方法を制御したりできます。

予定表オプションを使用すると、Teams Roomsの場所を整理できます。たとえば、特定の地理的な場所のユーザーの会議室のみを表示できます。 Outlook に表示できる会議室の容量やその他の情報を設定することもできます。

[手順 6 - 会議ポリシーを構成する](hybrid-meetings-device-config-policies.md)

[手順 7 - 予定表オプションを構成する](hybrid-meetings-device-config-calendar.md)

> [!div class="nextstepaction"]
> [次の手順](hybrid-meetings-device-config-license.md)