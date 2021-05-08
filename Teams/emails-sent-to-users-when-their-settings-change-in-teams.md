---
title: ユーザーの設定を変更したときに送信されるメール
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'ユーザーのダイヤルイン会議の設定が変更された場合に、ユーザーにメールで自動的に送信される情報Microsoft Teams。 '
ms.openlocfilehash: a9ca30e7e701afca2e42eccfaef4f3d45660cd3a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120758"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Microsoft Teams で設定を変更したときにユーザーに送信されるメール

電子メールは、電話会議プロバイダーとして Microsoft[](set-up-audio-conferencing-in-teams.md)を使用して電話会議が有効になっているユーザーに自動的に送信されます。

既定では、電話会議が有効になっているユーザーに送信される 4 種類のメールがあります。 ただし、ユーザーに送信されるメールの数を制限する場合は、オフにできます。 次の場合、Microsoft 365またはOffice 365電話会議は、ユーザーのメールにメールを送信します。

- **電話会議ライセンスが割り当てられるか、電話会議プロバイダーを Microsoft に変更するときに割り当てられます。**

     このメールには、会議 ID、会議の既定の電話会議電話番号、ユーザーの電話会議 PIN、ユーザーの既存の会議を更新するために使用される Skype for Business Online 会議更新ツールを使用する手順とリンクが含まれます。 「[アドオン ライセンスMicrosoft Teams割り当てる](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」または「Microsoft を電話会議プロバイダーとして割り[当てる」を参照してください](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

    > [!NOTE]
    > 組織で動的な会議 ID が有効になっている場合、スケジュールを設定したユーザーのすべての会議に固有の会議 ID が割り当てらされます。 組織で [電話会議の動的な ID を設定できます](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)。 

    このメールの例を次に示します。

     ![Skype for Businessライセンスの確認](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    ライセンスの詳細については、「Microsoft Teams[ライセンス」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

- **ユーザーの会議 ID または既定の電話会議電話番号が変更されます。**

    このメールには、会議 ID、既定の電話会議電話番号、およびユーザーの既存の会議を更新するために使用される Skype for Business Online 会議更新ツールを使用する手順とリンクが含まれている。 ただし、このメールにはユーザーの電話会議 PIN は含めになっていません。 「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」を参照してください。

    このメールの例を次に示します。

     ![ダイヤルイン会議情報が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **ユーザーの電話会議 PIN がリセットされます。**

    このメールには、開催者の電話会議 PIN、既存の会議 ID、ユーザーの既定の電話会議電話番号が含まれている。 「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」を参照してください。
    
     このメールの例を次に示します。
    
     ![ダイヤルイン会議 PIN が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **ユーザーのライセンスが削除される、または電話会議プロバイダーが Microsoft から他のプロバイダーまたはなしに変更された場合。**

    これは、電話会議ライセンス **が** ユーザーから削除された場合、または電話会議プロバイダーを [なし] に設定した場合に **発生します**。

    「[一Microsoft 365ライセンスの割り当てまたは削除」を参照してください](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

    このメールの例を次に示します。

     ![ダイヤルイン会議は無効になります。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>送信されるメール メッセージに変更を加える

ユーザーに自動的に送信されるメールを変更できます。 既定では、メールの送信者は Microsoft 365 または Office 365 から送信されますが、Windows PowerShell を使用して表示名を変更できます。 詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>メールを送信したくない場合は、どうしますか?

ユーザーへのメール送信を無効にすると、ユーザーにライセンスが割り当てられた場合でも、電子メールは送信されません。 この場合、会議 ID、既定の会議電話番号、さらに重要な点として、電話会議 PIN はユーザーに送信されません。 この場合は、ユーザーに別のメールを送信するか、ユーザーに電話で通知する必要があります。

既定では、メールはユーザーに送信されますが、電話会議のメールを受信したくない場合は、Microsoft Teams または Windows PowerShell を使用できます。 

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。

4. **[保存]** をクリックします。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Windows PowerShell を使用する**

詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。


## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

既定では、メールの送信者は Microsoft 365 または Office 365 から送信されますが、Windows PowerShell を使用してメール アドレスと表示名を変更できます。 

Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Windows PowerShell で Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。


## <a name="related-topics"></a>関連トピック

[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)