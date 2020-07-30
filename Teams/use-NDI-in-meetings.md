---
title: Microsoft Teams で NDI を使用する
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams で NDI を使用する方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d971a7c9e44e2fbf7c3d2500f237e3755c5f89d0
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522917"
---
# <a name="use-ndi-in-microsoft-teams"></a>Microsoft Teams で NDI を使用する

[!INCLUDE [template](includes/preview-feature.md)]

ネットワークデバイスインターフェイス (NDI) は、メディアデバイス (studio カメラやミキサーなど) に接続するための最新のソリューションです。 NDI は、物理接続を使う代わりに、ローカルコンピューター上など、ローカルイントラネット経由の接続を可能にします。

NewTek NDI®は、ストリームのライブコンテンツを生成するための標準的な業界ソリューションとなっており、プロフェッショナルなブロードキャスト世界で深刻な認知度と導入を実現しています。

Skype では、2018の遅刻で Skype に NDI アウト機能が追加されていました。 Microsoft Teams はこの機能を活用して、会議の操作性を向上させています。

NDI はローカルネットワークに限定され、ブロードキャストソリューションではなく、実稼働ワークフローの一部と見なされる必要があります。

## <a name="turn-on-ndi"></a>NDI を有効にする

NDI を有効にするには、ユーザーに対して2つの手順を実行する必要があります。

1. テナント管理者は、機能フラグ enableStreamingCallsOverNdi を有効にする必要があります。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. この変更が設定された後、エンドユーザーは、特定のクライアントに対して ndi を**設定**する必要があり  >  **Permissions**ます。

ユーザーが会議に参加すると、会議がブロードキャストされていることを知らせるメッセージが表示されます。 ユーザーがブロードキャストに含まれないようにする必要がある場合は、会議から削除する必要があります。

次の画像は、Teams 会議でユーザーに表示されるバナーメッセージを示しています。

![Teams 会議に表示される NDI バナーの画像。](media/NDI-disclosure.png)

バナーには[Microsoft のプライバシーポリシー](https://support.skype.com/faq/FA34853/what-is-skype-for-content-creators?q=ndi)へのリンクが含まれています。

## <a name="supported-locales-and-user-types"></a>サポートされるロケールとユーザーの種類

NDI は、すべてのロケールでサポートされています。 NDI 会議では、次のユーザーがサポートされています。

- テナント間–発信/テナント/ユーザー Id に基づいて提供される完全なサポート (会議ポリシー + 機能フラグによって制御されます)
- フェデレーション–いいえ (NDI を使用していても)<sup>1</sup>
- 目につき-いいえ (既定値)
- 匿名–いいえ (既定値)
- Guest – no (既定値)

<sup>1 つ</sup>のデバイスには、既定でオンになっている ndi 設定があります。 会議の出席者が NDI off のデバイスを使用している場合は、NDI を有効にする必要があります。
