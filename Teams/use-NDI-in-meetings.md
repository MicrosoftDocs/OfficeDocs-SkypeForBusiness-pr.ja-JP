---
title: 会議のコンテンツをブロードキャストする
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: NDI と SDI を使用して Microsoft Teams で会議コンテンツをブロードキャストする方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc185a22c7ea4d849008989da29f50a8f98ebb9d
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706814"
---
# <a name="broadcast-meeting-content"></a>会議のコンテンツをブロードキャストする 



Teams には、Teams 会議コンテンツをブロードキャストするための 2 つのオプションがあります。ネットワーク デバイス インターフェイス (NewTek NDI®) とシリアル デジタル インターフェイス (SDI):

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


エンド ユーザーを有効にするには、Teams 管理 センターまたは Teams PowerShell を次のように使用できます。

Teams 管理センターで、 **オーディオ & ビデオ>会議ポリシー** に移動し、[ **ローカルブロードキャスト**] を選択します。

PowerShell を使用するには、次のようにSet-CsTeamsMeetingPolicyコマンドレットを使用します。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

この変更が設定されたら、エンド ユーザーは **設定** > **アクセス許可** から特定のクライアントのローカル ストリーミングを有効にする必要があります。 詳細については、「 [Teams からのオーディオとビデオのブロードキャスト](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3)」を参照してください。





