---
title: ユーザーの設定を変更したときに送信されるメール
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'ダイヤルイン会議の設定がMicrosoft Teamsで変更されたときに、ユーザーに電子メールで自動的に送信される情報について説明します。 '
ms.openlocfilehash: 81faefb3bfe2fd6c93584c5a9f48fd99a6040c99
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055477"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Microsoft Teams で設定を変更したときにユーザーに送信されるメール

電子メールは、電話会議プロバイダーとして Microsoft を使用して [電話会議が有効になっている](set-up-audio-conferencing-in-teams.md) ユーザーに自動的に送信されます。

既定では、電話会議が有効になっているユーザーに送信される電子メールの種類は 4 つあります。 ただし、ユーザーに送信されるメールの数を制限する場合は、無効にできます。 Microsoft 365またはOffice 365の電話会議では、次の場合にユーザーの電子メールに電子メールが送信されます。

- **電話会議ライセンスが割り当てられるか、電話会議プロバイダーを Microsoft に変更する場合。**

     この電子メールには、会議 ID、会議の既定の会議電話番号、ユーザーの電話会議 PIN、およびユーザーの既存の会議の更新に使用されるSkype for Businessオンライン会議更新ツールを使用するための手順とリンクが含まれます。 「[アドオン ライセンスMicrosoft Teams割り当てる](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」または「[Microsoft を電話会議プロバイダーとして割り当てる」を参照してください](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

    > [!NOTE]
    > 組織で動的会議 ID が有効になっている場合、スケジュール設定されたすべてのユーザーの会議には、一意の会議 ID が設定されます。 [組織内で電話会議の動的 ID を](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)設定できます。

    この電子メールの例を次に示します。

     ![ライセンスSkype for Business確認します。](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    ライセンスの詳細については、「[アドオン ライセンスMicrosoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)参照してください。

- **ユーザーの会議 ID または既定の会議電話番号が変更されます。**

    この電子メールには、会議 ID、既定の会議電話番号、およびユーザーの既存の会議を更新するために使用されるSkype for Businessオンライン会議更新ツールを使用するための手順とリンクが含まれています。 ただし、このメールにはユーザーの電話会議 PIN は含まれません。 「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」を参照してください。

    この電子メールの例を次に示します。

     ![ダイヤルイン会議情報が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **ユーザーの電話会議 PIN がリセットされます。**

    この電子メールには、開催者の電話会議 PIN、既存の会議 ID、およびユーザーの既定の会議電話番号が含まれています。 「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」を参照してください。

     この電子メールの例を次に示します。

     ![ダイヤルイン会議の PIN が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **ユーザーのライセンスが削除されるか、電話会議プロバイダーが Microsoft から他のプロバイダーまたは None に変更された場合。**

    これは、 **電話会議** ライセンスがユーザーから削除されたとき、または電話会議プロバイダーを **None** に設定するときに発生します。

    [ビジネス向けのMicrosoft 365のライセンスの割り当てまたは削除に関するページを](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)参照してください。

    この電子メールの例を次に示します。

     ![ダイヤルイン会議はオフになっています。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>送信される電子メール メッセージに変更を加える

ユーザーに自動的に送信されるメールに変更を加えることができます。 既定では、電子メールの送信者はMicrosoft 365またはOffice 365から送信されますが、Windows PowerShellを使用して表示名を変更できます。 詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>メールを送信したくない場合はどうなりますか?

ユーザーへの電子メールの送信を無効にすると、ユーザーにライセンスが割り当てられた場合でも、電子メールは送信されません。 この場合、会議 ID、既定の会議電話番号、さらに重要な点として、電話会議 PIN はユーザーに送信されません。 このような場合は、ユーザーに個別のメールを送信するか、またはそれらを呼び出してユーザーに伝える必要があります。

既定では、電子メールはユーザーに送信されますが、電話会議の電子メールを受信できないようにする場合は、Microsoft TeamsまたはWindows PowerShellを使用できます。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。

3. [**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。

4. **[保存]** をクリックします。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Windows PowerShell の使用

Microsoft Teams PowerShell モジュールを使用して、次を実行することもできます。

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Windows PowerShell を使用して、次を実行することもできます。[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings)

詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

既定では、電子メールの送信者はMicrosoft 365またはOffice 365から送信されますが、Windows PowerShellを使用してメール アドレスと表示名を変更できます。

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあります。Windows PowerShell があれば、一元管理を使用して Microsoft 365 または Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。

- [Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell で Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。

## <a name="related-topics"></a>関連トピック

[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
