---
title: Teams Android デバイスの自動応答を設定する
author: mkbond007
ms.author: mabond
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
description: PowerShell を使用してAndroidでMicrosoft Teams Roomsの自動応答機能を設定し、ビデオ電話デバイスをTeamsする方法について説明します。
ms.openlocfilehash: fac458a2b7b100a2074dbaac0e209fbdd3527eef
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646596"
---
# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>AndroidおよびTeamsビデオ電話デバイスでMicrosoft Teams Roomsの自動応答を設定する

この記事では、ビデオ電話デバイスのAndroidとTeamsのMicrosoft Teams Roomsで自動応答機能を設定する場合に役立ちます。 自動応答を使用すると、管理者特権を持つ組織内のユーザーは、デバイス設定を変更して、受信会議の招待を自動的に受け入れ、ビデオを使用して通話を自動的に受け入れます。

## <a name="enable-auto-answer-with-powershell"></a>PowerShell で自動回答を有効にする

次の属性を使用して、ビデオ電話デバイスのAndroidとTeamsのMicrosoft Teams Roomsで自動応答を有効にします。

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. 受信会議の招待に対する自動応答を有効にする

**Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** を使用して、受信会議の招待に対する自動応答を有効にします。 自動回答は既定で **オフになっています** 。 このポリシーは、受信会議の招待にのみ適用され、他の通話の種類はサポートされません。 コマンドレットの詳細については、 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) を参照してください。

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. デバイス サインイン モードを設定する

**Set-CsTeamsIPPhonePolicy -SignInMode** を使用して、デバイスのサインイン モードを設定して、Teamsにサインインするときの動作を決定します。 コマンドレットの詳細については、 [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) を参照してください。

サインイン モードには、次の 3 つのオプションがあります。

- **UserSignIn:** 電話で個々のユーザー Teams エクスペリエンスを有効にします。
- **CommonAreaPhoneSignIn:** 電話で共通エリアの電話エクスペリエンスを有効にします。
- **MeetingSignIn:** 電話で会議室エクスペリエンスを有効にします。

たとえば、次のポリシーは、サインイン モードを会議室エクスペリエンスに設定します。

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>デバイス設定を構成する

自動回答を有効にした後、管理者権限を持つユーザーは、デバイス設定で機能を有効にすることができます。 デバイス レベルでこの機能を有効にするには、 **受信会議の招待を自動承諾** するをオンにする必要があります。 **ビデオで自動承諾** を有効にすることもできます。 どちらの設定も既定ではオフになっています。

## <a name="related-topics"></a>関連項目

[Microsoft サポート: 通話とデバイス](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
