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
ms.openlocfilehash: eebbea6ce5d632d38e94465f05fd9f60a3300a4e060106e7ba2f6218433c5e8b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335817"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>NDI の®を使用Microsoft Teams

 NewTek NDI® (ネットワーク デバイス インターフェイス) テクノロジは、メディア デバイス (スタジオ カメラやミキサーなど) を接続するための最新のソリューションです。 NDI® テクノロジでは、物理的な接続を使用する代わりに、ローカル コンピューターを含むローカル イントラネットを使用して接続できます。

NDI®は、ストリームのライブ コンテンツを生成するための標準的な業界標準ソリューションになり、プロのブロードキャストの世界で大きな認識と導入を獲得しています。

Skype 2018 年後半に NDI ®アウト機能が追加Skypeに追加されました。 Microsoft Teamsこの機能を使用して、会議のエクスペリエンスを向上します。

NDI®はローカル ネットワークに限定され、ブロードキャスト ソリューションではなく、実稼働ワークフローの一部と見なす必要があります。

## <a name="turn-on-ndi-technology"></a>NDI テクノロジを有効®する

NDI®、ユーザーに対して 2 つの手順を有効にする必要があります。

1. テナント管理者は、CsTeamsMeetingPolicy で "AllowNDIStreaming" プロパティを有効にする必要があります。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. この変更が設定された後、エンド ユーザーは、特定のクライアントの NDI ® テクノロジを[アクセス許可] から有効設定  >  **があります**。

ユーザーが会議に参加すると、会議がブロードキャスト中であることの通知メッセージが表示されます。 ユーザーをブロードキャストに含めたくない場合は、会議から削除する必要があります。

次の図は、ユーザーが会議中に表示するバナー メッセージTeamsしています。

![彼は、®に表示される NDI の技術バナー Teamsします。](media/NDI-disclosure.png)

バナーには、Microsoft のプライバシー ポリシー [へのリンクがあります](https://aka.ms/teamsprivacy)。

> [!NOTE]
> NDI®セッションごとにのみアクティブ化されます。 次のログインでは、ユーザーは NDI を使用する前にアクティブ化する®。

## <a name="supported-locales-and-user-types"></a>サポートされている地域とユーザーの種類

NDI®は、すべての地域でサポートされています。 NDI テクノロジ ストリームには次のユーザー®含まれますが、すべてのユーザーが NDI テクノロジ ストリームにアクセス®はありません。

- テナント内 – リング/tenantId/userId に基づいて配信される完全なサポート (会議ポリシーによって制御)
- フェデレーション – ストリーム アクセスなし (NDI テクノロジ®場合でも)<sup>1</sup>
- プレミアム - ストリーム アクセスなし
- 匿名 – ストリーム アクセスなし
- ゲスト – ストリーム アクセスなし  

<sup>1</sup> デバイスには、既定でオン® NDI のテクノロジ設定があります。 会議の参加者が NDI テクノロジをオフにしたデバイス®場合は、NDI テクノロジを有効にする®があります。
