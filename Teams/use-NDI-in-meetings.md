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
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598466"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Microsoft Teams で NDI ®テクノロジを使用する

 NewTek NDI® (ネットワーク デバイス インターフェイス) テクノロジは、メディア デバイス (スタジオ カメラや Mixer など) を接続するための最新のソリューションです。 NDI® テクノロジでは、物理的な接続を使用する代わりに、ローカル コンピューターを含むローカル イントラネットを使用して接続できます。

NDI®テクノロジは、ストリーム用のライブ コンテンツを生成するための標準的な業界標準ソリューションであり、プロのブロードキャストの世界で大きな認知度と導入を獲得しています。

Skype は、2018 ®に NDI の機能を Skype に追加しました。 Microsoft Teams はこの機能を使用して、会議のエクスペリエンスを向上します。

NDI®テクノロジはローカル ネットワークに限定され、ブロードキャスト ソリューションではなく、実稼働ワークフローの一部としてのみ考慮する必要があります。

## <a name="turn-on-ndi-technology"></a>NDI テクノロジを®する

NDI®は、ユーザーに対して 2 つの手順を有効にする必要があります。

1. テナント管理者は、CsTeamsMeetingPolicy で "AllowNDIStreaming" プロパティを有効にする必要があります。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. この変更が設定された後、エンド ユーザーは[設定のアクセス許可] から特定® NDI テクノロジを有効 **にする**  >  **必要があります**。

ユーザーが会議に参加すると、会議がブロードキャストされるというメッセージが表示されます。 ユーザーがブロードキャストに含めたくない場合は、会議から削除する必要があります。

次の画像は、Teams 会議でユーザーに表示されるバナー メッセージを示しています。

![彼は、Teams ®に表示される NDI のテクノロジ バナーです。](media/NDI-disclosure.png)

バナーには、Microsoft プライバシー ポリシーへの [リンクがあります](https://aka.ms/teamsprivacy)。

> [!NOTE]
> NDI®セッションごとにのみアクティブ化されます。 次のログイン時に、ユーザーは NDI を使用する前にライセンス認証を®。

## <a name="supported-locales-and-user-types"></a>サポートされている地域とユーザーの種類

NDI®技術は、すべての地域でサポートされています。 NDI テクノロジ ストリームには次の®ユーザーが含まれますが、すべてのユーザーが NDI テクノロジ ストリームに®できるではありません。

- テナント内 – リング/tenantId/userId に基づいて配信される完全なサポート (会議ポリシーによって制御されます)
- フェデレーション – ストリーム アクセスなし (NDI を持っている場合®テクノロジがオンの場合でも)<sup>1</sup>
- Premium - ストリーム アクセスなし
- 匿名 – ストリーム アクセスなし
- ゲスト – ストリーム アクセスなし  

<sup>1</sup> デバイスには、既定®有効な NDI テクノロジ設定があります。 会議の参加者が NDI を使用している場合、®をオフにしている場合は、NDI テクノロジを®があります。
