---
title: Android デバイスの自動応答Teams設定する
author: KarliStites
ms.author: kastites
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: kponnus
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: PowerShell を使用して Android デバイスの自動応答機能Teamsを設定する方法について説明します。
ms.openlocfilehash: e25b0694b54d1047c64ecaba026380ac9c4a9949
ms.sourcegitcommit: 5e9a8d3cdb72b57adfb842200159c5d753b70ecb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2022
ms.locfileid: "62329102"
---
# <a name="set-up-auto-answer-for-teams-android-devices"></a>Android デバイスの自動応答Teams設定する

この記事は、Android デバイスで自動応答機能を設定Teams役立ちます。 自動応答を使用すると、管理者特権を持つ組織内のユーザーは、自分のデバイス設定を変更して、着信会議の招待を自動的に受け入れ、ビデオを使用して自動的に通話を受け入れできます。

## <a name="enable-auto-answer-with-powershell"></a>PowerShell で自動回答を有効にする

次の属性を使用して、Android デバイスで自動Teamsを有効にします。

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. 会議出席招待の自動応答を有効にする

**Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** を使用して、会議出席招待の自動応答を有効にできます。 既定では、 **自動回答は** オフになっています。 このポリシーは、会議出席招待の着信にのみ適用され、他の通話の種類はサポートされていません。 コマンドレット [の詳細については、「Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) 」を参照してください。

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. デバイスのサインイン モードを設定する

**Set-CsTeamsIPPhonePolicy -SignInMode** を使用して、デバイスのサインイン モードを設定して、Teams にサインインするときに動作を決定します。 コマンドレット [の詳細については、「Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) 」を参照してください。

サインイン モードには、次の 3 つのオプションがあります。

- **UserSignIn:** 個々のユーザーが電話Teamsエクスペリエンスを有効にする。
- **CommonAreaPhoneSignIn:** 電話での一般的なエリア電話エクスペリエンスを有効にする。
- **MeetingSignIn:** 電話での会議室の操作を有効にする。

たとえば、次のポリシーは、サインイン モードを会議室のエクスペリエンスに設定します。

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>デバイス設定を構成する

自動回答を有効にすると、管理者アクセス許可を持つユーザーは、デバイス設定で機能を有効にできます。 デバイス レベルで機能を有効にするには、[会議出席招待の自動承諾] **をオンにする必要があります**。 ビデオで自動承諾 **を有効にできます**。 既定では、両方の設定がオフになっています。

## <a name="related-topics"></a>関連項目

[Microsoft サポート: 通話とデバイス](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)