---
title: 会議の内容をブロードキャストする
author: CarolynRowe
ms.author: crowe
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: NDI と SDI を使用して、会議コンテンツをブロードキャストする方法についてMicrosoft Teams。
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
# <a name="broadcast-meeting-content"></a>会議の内容をブロードキャストする 



Teamsには、ネットワーク デバイス インターフェイス (NewTek NDI®Teams) とシリアル デジタル インターフェイス (SDI) の 2 つのオプションがあります。

- NewTek NDI® テクノロジは、メディア デバイス (スタジオ カメラやミキサーなど) を接続するための最新のソリューションです。 NDI® テクノロジでは、物理的な接続を使用する代わりに、ローカル コンピューターを含むローカル イントラネットを使用して接続できます。

  NDI®は、ストリームのライブ コンテンツを生成するための標準的な業界標準ソリューションになり、プロのブロードキャストの世界で大きな認識と導入を獲得しています。

- SDI は 1989 年からブロードキャスト制作で使用され、ほとんどのレガシ スタジオ ハードウェア デバイスでサポートされています。 AJA Video Systems と Blackmagic Design のハードウェア デバイスは、SDI を使用する従来のブロードキャスト デバイスへの接続を提供します。

> [!NOTE]
> SDI をサポートするビデオ ハードウェアアウト機能は、現在プレビュー リリース中です。

NDI® SDI テクノロジは、すべての地域でサポートされています。

NDI と SDI の使用へのアクセスは、機能のアクティブ化を試みるユーザーの会議ポリシーによって決まります。 最も安全なソリューションの場合は、グローバル設定としてローカル ストリーミング パラメーターを有効にすることはできません。


## <a name="enable-broadcast-features"></a>ブロードキャスト機能を有効にする

ユーザーに対して NDI ® SDI ブロードキャスト機能を有効にするには:

1. テナント管理者は、エンド ユーザーが会議ポリシーのローカル ストリーミングを有効にする必要があります。 

2. エンド ユーザーは、特定のクライアントのローカル ストリーミングを有効にする必要があります。


エンド ユーザーを有効にするには、次のように管理センター Teams使用するか、PowerShell Teamsを使用します。

[Teams 管理センターで、[音声] ビデオの **[会議** ポリシー>] &し、[NDI ストリーミングを許可する]**を選択します**。

PowerShell を使用するには、次のように Set-CsTeamsMeetingPolicy コマンドレットを使用します。

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

この変更が設定された後、エンド ユーザーは特定のクライアントのローカル ストリーミングを[アクセス許可] からオン設定  >  **必要があります**。 詳細については、オーディオとビデオの配信[に関するページを参照Teams。](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3)





