---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593664"
---
作業を開始する前に、次の前提条件があることを確認します。

- Blue Yonder WFM バージョン 2020.3、2021.1、または 2021.2。

    > [!NOTE]
    > Blue Yonder WFM 2020.3 または 2021.1 がある場合は、2020.3.0.4 または 2021.1.0.3 パッチを適用します。 この修正プログラムは、ユーザーが Shifts で永続的なエラー メッセージを受け取る問題を修正します。 また、ユーザーが Shifts で可用性を更新できない問題も修正されます。

- Blue Yonder WFM サービス アカウント名とパスワードとサービス URL:

    - フェデレーション認証 URL
    - Cookie 認証 URL
    - 従業員セルフサービス URL
    - Retail web API URL
    - サイト マネージャー API URL
    - 管理 API URL

    この情報がない場合は、Blue Yonder サポートにお問い合わせください。 このアカウントは、Blue Yonder エンタープライズ管理者によってルートエンタープライズ レベルで作成されます。 API Access、クライアント管理者、および Store Manager アクセス権が必要です。 接続を作成するには、アカウントとパスワードが必要です。
- フェデレーション SSO 認証は、Blue Yonder WFM 環境で有効になっています。 フェデレーション SSO が有効になっていることを確認するには、Blue Yonder サポートにお問い合わせください。 次の情報が必要になります。

    - federatedSSOValidationService: `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` {tenantId} が tenantId である場合
     - proxyHeader: X-MS-AuthToken

- Teamsに少なくとも 1 つのチームが設定されています。
- マップするすべてのチームに、Microsoft 365 システム アカウントをチーム所有者として追加しました。</br> [Microsoft 365でこのアカウントを作成](/microsoft-365/admin/add-users/add-users)し、Microsoft 365 ライセンスを割り当てます。 次に、マップするすべてのチームにチーム所有者としてアカウントを追加します。 Shifts コネクタは、Blue Yonder WFM から Shifts の変更を同期するときに、このアカウントを使用します。

    この目的のために特別にアカウントを作成し、ユーザー アカウントを使用しないことをお勧めします。