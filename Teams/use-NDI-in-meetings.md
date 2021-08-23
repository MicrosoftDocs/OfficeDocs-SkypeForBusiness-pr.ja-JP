---
title: NDI を使用Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams で NDI を使用する方法についてMicrosoft Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a9eed33ba105584379f207697c27e8d6bd6cde5
ms.sourcegitcommit: 85017cf88789c750836780dad2ef707c1c6c39b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58359184"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>NDI の®を使用Microsoft Teams

 NewTek NDI® (ネットワーク デバイス インターフェイス) テクノロジは、メディア デバイス (スタジオ カメラやミキサーなど) を接続するための最新のソリューションです。 NDI® テクノロジでは、物理的な接続を使用する代わりに、ローカル コンピューターを含むローカル イントラネットを使用して接続できます。

NDI®は、ストリームのライブ コンテンツを生成するための標準的な業界標準ソリューションになり、プロのブロードキャストの世界で大きな認識と導入を獲得しています。

Skype 2018 年後半に NDI ®アウト機能が追加Skype追加されました。 Microsoft Teamsこの機能を使用して、会議のエクスペリエンスを向上します。

NDI®はローカル ネットワークに限定され、ブロードキャスト ソリューションではなく、実稼働ワークフローの一部としてのみ考慮する必要があります。

## <a name="turn-on-ndi-technology"></a>NDI テクノロジを有効®する

NDI®、ユーザーに対して 2 つの手順を有効にする必要があります。

1. テナント管理者は、エンド ユーザーが会議ポリシーに対して NDI を有効にする必要があります。 これは、Teams 管理ポータルまたは CsTeamsMeetingPolicy の _AllowNDIStreaming_ プロパティによって Teams PowerShell を使用して個別に実行できます。

    ```PowerShell
    Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
    ```

2. この変更が設定された後、エンド ユーザーは、特定のクライアントの NDI ® テクノロジを[アクセス許可] から有効設定  >  **必要があります**。

ユーザーとその特定のクライアントに対してオンにした後、ユーザーはオーバーフロー メニューを使用して [NDI 経由でブロードキャスト] を選択して NDI を有効にできます。

NDI を開始し、エンドポイントが NDI フィードをサブスクライブすると、会議がブロードキャスト中であることの通知メッセージが表示されます。 ユーザーをブロードキャストに含めたくない場合は、会議から削除する必要があります。

次の図は、ユーザーが会議中に表示するバナー メッセージTeamsしています。

![NDI は®会議に表示される技術バナー Teamsします。](media/NDI-disclosure.png)

バナーには、Microsoft のプライバシー ポリシー [へのリンクがあります](https://aka.ms/teamsprivacy)。

> [!NOTE]
> NDI®セッションごとにのみアクティブ化されます。 次の会議では、ユーザーは NDI を使用する前にアクティブ化する®。

## <a name="supported-locales-and-user-types"></a>サポートされている地域とユーザーの種類

NDI®は、すべての地域でサポートされています。

NDI を使用するアクセスは、機能のアクティブ化を試みるユーザーの会議ポリシーによって決まります。 最も安全なソリューションでは、グローバル設定として NDI ポリシーを有効にしない。
