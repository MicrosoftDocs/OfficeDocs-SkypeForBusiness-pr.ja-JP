---
title: 会議のコンテンツをブロードキャストする
author: CarolynRowe
ms.author: crowe
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teamsで NDI と SDI を使用して会議のコンテンツをブロードキャストする方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65e47ccfa1963e8e95e13a1c8b94e1e051ff709c
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2021
ms.locfileid: "59941882"
---
# <a name="broadcast-meeting-content"></a>会議のコンテンツをブロードキャストする 



Teamsには、会議コンテンツTeamsブロードキャストするための 2 つのオプションが用意されています。ネットワーク デバイス インターフェイス (NewTek NDI®) とシリアル デジタル インターフェイス (SDI):

- NewTek NDI® テクノロジは、メディア デバイス (スタジオ カメラやミキサーなど) を接続するための最新のソリューションです。 物理接続を使用する代わりに、NDI® テクノロジを使用すると、ローカル コンピューターを含むローカル イントラネット経由での接続が可能になります。

  NDI® テクノロジは、ストリーム用のライブ コンテンツを生成するための標準的な業界ソリューションとなり、プロのブロードキャストの世界で大きな認識と導入を得ています。

- SDI は 1989 年からブロードキャスト運用で使用されており、ほとんどの従来のスタジオ ハードウェア デバイスでサポートされています。 AJA Video Systems および Blackmagic Design のハードウェア デバイスは、SDI を使用するレガシ ブロードキャスト デバイスへの接続を提供します。

> [!NOTE]
> SDI をサポートする Video Hardware Out 機能は、現在プレビュー リリース中です。

NDI® と SDI テクノロジは、すべてのロケールでサポートされています。

NDI と SDI の使用へのアクセスは、機能をアクティブ化しようとしているユーザーの会議ポリシーによって決まります。 最も安全なソリューションの場合は、ローカル ストリーミング パラメーターをグローバル設定としてオンにしないでください。


## <a name="enable-broadcast-features"></a>ブロードキャスト機能を有効にする

ユーザーに対して NDI® および SDI ブロードキャスト機能を有効にするには、次の手順を実行します。

1. テナント管理者は、エンド ユーザーが会議ポリシーに対してローカル ストリーミングを有効にする必要があります。 

2. エンド ユーザーは、特定のクライアントのローカル ストリーミングを有効にする必要があります。


エンド ユーザーを有効にするには、次のようにTeams管理センターまたは powerShell Teamsを使用できます。

Teams管理センターで、**オーディオ & ビデオ>会議ポリシー** に移動し、[**NDI ストリーミングを許可する**] を選択します。

PowerShell を使用するには、次のようにSet-CsTeamsMeetingPolicyコマンドレットを使用します。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

この変更が設定されたら、エンド ユーザーは特定のクライアントのローカル ストリーミング **を 設定** > **Permissions** から有効にする必要があります。 詳細については、「[Teamsからのオーディオとビデオのブロードキャスト](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3)」を参照してください。





