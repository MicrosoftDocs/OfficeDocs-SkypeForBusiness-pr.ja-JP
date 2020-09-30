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
ms.openlocfilehash: a1b756cfdb56de533d4dd170f301dc38e4b3b529
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308170"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Microsoft Teams で NDI®テクノロジを使用する

 NewTek NDI® (Network Device Interface) テクノロジは、メディアデバイス (スタジオカメラやミキサーなど) に接続するための最新のソリューションです。 NDI®テクノロジを使用する代わりに、ローカルコンピューター上など、ローカルイントラネット経由での接続を可能にします。

NDI®テクノロジは、ストリームのライブコンテンツを生成するための標準的な業界ソリューションとなっており、プロフェッショナルなブロードキャスト世界で深刻な認知度と導入を実現しています。

Skype では、2018遅刻の Skype に NDI®機能が追加されました。 Microsoft Teams では、この機能を使用して、会議の操作性を向上させています。

NDI®テクノロジはローカルネットワークに限定され、ブロードキャストソリューションではなく、運用ワークフローの一部と見なされる必要があります。

## <a name="turn-on-ndi-technology"></a>NDI®テクノロジを有効にする

NDI®テクノロジを有効にするには、2つの手順をユーザーに対して行う必要があります。

1. テナント管理者は、CsTeamsMeetingPolicy で ' AllowNDIStreaming ' プロパティを有効にする必要があります。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. この変更が設定された後、エンドユーザーは、特定のクライアントの [**設定**] 権限から ndi®テクノロジを有効にする必要があり  >  **Permissions**ます。

ユーザーが会議に参加すると、会議がブロードキャストされていることを知らせるメッセージが表示されます。 ユーザーがブロードキャストに含まれないようにする必要がある場合は、会議から削除する必要があります。

次の画像は、Teams 会議でユーザーに表示されるバナーメッセージを示しています。

![Teams 会議に表示される NDI®技術バナーの画像。](media/NDI-disclosure.png)

バナーには [Microsoft のプライバシーポリシー](https://aka.ms/teamsprivacy)へのリンクが含まれています。

## <a name="supported-locales-and-user-types"></a>サポートされるロケールとユーザーの種類

NDI®テクノロジは、すべてのロケールでサポートされています。 次のユーザーは、NDI®テクノロジストリームに含まれていますが、すべてのユーザーが NDI®テクノロジストリームにアクセスできるわけではありません。

- テナント間–発信/テナント/ユーザー Id に基づいて提供される完全なサポート (会議ポリシーによって制御されます)
- フェデレーション–ストリームアクセスなし (NDI®テクノロジを使用していても)<sup>1</sup>
- 目につき-ストリームアクセスなし
- 匿名–ストリームにアクセスできません。
- ゲスト–ストリームへのアクセスはありません。  

<sup>1 つ</sup> のデバイスには、既定でオンになっている ndi®テクノロジ設定があります。 会議の出席者が NDI®テクノロジを使用していないデバイスを使っている場合は、NDI®テクノロジを有効にする必要があります。
