---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593664"
---
開始する前に、次の前提条件を満たしていることを確認してください。

- Blue Yonder WFM バージョン 2020.3、2021.1、または 2021.2。

    > [!NOTE]
    > Blue Yonder WFM 2020.3 または 2021.1 を使用している場合は、2020.3.0.4 または 2021.1.0.3 パッチを適用します。 この修正プログラムは、ユーザーが Shifts で永続的なエラー メッセージを受け取る問題を修正します。 また、ユーザーが Shifts で可用性を更新できる問題も修正されます。

- Blue Yonder WFM サービス アカウント名とパスワードとサービス URL:

    - フェデレーション認証 URL
    - Cookie 認証 URL
    - 従業員のセルフサービス URL
    - Retail web API URL
    - Site manager API URL
    - 管理 API URL

    この情報をお持ちでない場合は、Blue Yonder サポートにお問い合わせください。 このアカウントは、Blue Yonder エンタープライズ管理者によってルート エンタープライズ レベルで作成されます。 API アクセス、クライアント管理者、および Store Manager アクセス権が必要です。 接続を作成するには、アカウントとパスワードが必要です。
- フェデレーション SSO 認証は、Blue Yonder WFM 環境で有効になっています。 フェデレーション SSO が有効になっているか確認するには、Blue Yonder サポートにお問い合わせください。 次の情報が必要です。

    - federatedSSOValidationService: `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` ここで、{tenantId} は tenantId です
     - proxyHeader: X-MS-AuthToken

- 少なくとも 1 つのチームが Teams。
- マップするチームMicrosoft 365アカウントをチーム所有者として追加しました。</br> [このアカウントを作成しMicrosoft 365](/microsoft-365/admin/add-users/add-users)ライセンスを割りMicrosoft 365します。 次に、マップするすべてのチームにチーム所有者としてアカウントを追加します。 Shifts コネクタは、Shifts の同期が Blue Yonder WFM から変更される場合に、このアカウントを使用します。

    この目的専用のアカウントを作成し、ユーザー アカウントを使用しない方法をお勧めします。