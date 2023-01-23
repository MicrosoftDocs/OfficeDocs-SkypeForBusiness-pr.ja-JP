---
title: 機密性の高い Teams 会議に透かしを要求する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: 機密性の高い Teams 会議で出席者のビデオと共有コンテンツに透かしを有効または要求する方法について説明します。
ms.openlocfilehash: 6037bc6e9dbe79d9ecee10666f4c34e4e778216a
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950504"
---
# <a name="require-a-watermark-for-sensitive-teams-meetings"></a>機密性の高い Teams 会議に透かしを要求する

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

画面で共有されるコンテンツと出席者のビデオの両方について、Teams 会議に透かしを表示できます。 透かしには、会議参加者のメール アドレスが表示されます。 会議の参加者は透かしをオフにできません。

透かしは、Teams デスクトップとモバイルでサポートされています。 サポートされていないプラットフォームから会議に参加People、オーディオのみのエクスペリエンスが得られます。

[Cloud Video Interop (CVI)](cloud-video-interop.md) から参加する参加者は、透かしなしでコンテンツを表示できます。

透かしが使用されている場合、次の参加者はオーディオのみのエクスペリエンスを持っています。

- Teams Web クライアントを使用する参加者
- Virtual Desktop Infrastructure (VDI) 参加者
- 匿名の参加者
- オーバーフロー参加者
- Windows 上のMicrosoft Teams Roomsと Surface Hub のMicrosoft Teams Rooms
- Android でのMicrosoft Teams Rooms
- 以前の Teams クライアント
- [Microsoft Teams Rooms デバイスでの直接ゲスト参加](/microsoftteams/rooms/third-party-join)

> [!Note]
> 秘密度ラベル、カスタム会議テンプレート、透かしの会議設定には、Teams Premiumが必要です。

会議の透かしは、Teams 管理センターで有効になります。 その後、会議の開催者によって追加されるか、テンプレートまたは秘密度ラベルによって適用されます。

次の表は、透かしが構成されている場所を示しています。

|Setting|管理 ポリシー|秘密度ラベル|テンプレート|会議の開催者|
|:------|:----------:|:---------------:|:------:|:---------------:|
|共有コンテンツに透かしを適用する|はい|Yes|Yes|Yes|
|すべてのユーザーのビデオ フィードに透かしを適用する|Yes|Yes|Yes|Yes|

会議で透かしが使用されている場合は、次の機能がオフになります。

- 会議の記録 (自動記録を含む)

- 大きなギャラリー

- Together モード

- PowerPoint Live

- ホワイトボード

- カメラからのコンテンツ

## <a name="watermarks-for-sensitive-and-highly-sensitive-meetings"></a>機密性が高く機密性の高い会議の透かし

透かしは、会議で共有される機密情報を保護するのに役立ちます。 これは、通常は情報にアクセスできないユーザーと情報を共有する場合に最も便利です。 たとえば、財務組織のメンバーは、四半期ごとの見積もりをさまざまな部門のマネージャーと共有するときに透かしを使用する場合があります。

透かしは機密情報が流出する可能性を減らすために設計されているため、すべての参加者が共有されているコンテンツに直接アクセスできる会議で使用しても、セキュリティが強化されない可能性があります。

他の会議機能で透かしを使用して会議の機密情報を保護する方法については、「 [機密性の高いデータを保護して Teams 会議を構成する](/microsoftteams/configure-meetings-highly-sensitive-protection)」を参照してください。

## <a name="enable-watermarks"></a>透かしを有効にする

テンプレートと秘密度ラベルで透かしを使用できるようにするには、会議の開催者に対して、Teams 管理センターで透かしを有効にする必要があります。

会議の透かしを有効にするには

1. Teams 管理センターで、[ **会議** ] を展開し、[ **会議ポリシー**] を選択します。

1. 更新するポリシーを選択します。

1. 出席者のビデオで透かしを有効にするには、[ **透かしビデオ]** を **[オン]** に設定します。

1. 会議で画面上で共有されているコンテンツで透かしを有効にするには、[ **透かし共有コンテンツ]** を **[オン]** に設定します。

    ![透かしの Teams 管理者ポリシーのスクリーンショット](media/watermark-admin-policy.png)

1. 透かしがデスクトップおよびモバイル デバイスでどのように表示されるかを確認するには、[ **プレビュー**] を選択します。

1. **[保存]** を選択します。

PowerShell を使用して透かしを有効または無効にすることもできます。 パラメーターと `-AllowWatermarkForScreenSharing` パラメーターを指定して [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) コマンドレットを`-AllowWatermarkForCameraVideo`使用します。

次に例を示します。

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForCameraVideo $True 

Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForScreenSharing $True 
```

## <a name="related-topics"></a>関連項目

[3 層の保護を使用して Teams 会議を構成する](configure-meetings-three-tiers-protection.md)

[Teams 会議テンプレート、秘密度ラベル、管理ポリシーを組み合わせて機密性の高い会議に使用する](meeting-templates-sensitivity-labels-policies.md)
