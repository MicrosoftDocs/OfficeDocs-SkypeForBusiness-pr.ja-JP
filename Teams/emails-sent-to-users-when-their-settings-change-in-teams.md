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
description: 'Microsoft Teams でダイヤルイン会議の設定が変更された場合に、ユーザーにメールで自動的に送信される情報について説明します。 '
ms.openlocfilehash: a9ca30e7e701afca2e42eccfaef4f3d45660cd3a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120758"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Microsoft Teams で設定を変更したときにユーザーに送信されるメール

Microsoft を電話会議プロバイダーとして使用して電話[](set-up-audio-conferencing-in-teams.md)会議を有効にしているユーザーにメールが自動的に送信されます。

既定では、電話会議が有効になっているユーザーに 4 種類のメールが送信されます。 ただし、ユーザーに送信されるメールの数を制限する場合は、この機能をオフにできます。 Microsoft 365 または Office 365 の電話会議では、次の場合にメールがユーザーのメールに送信されます。

- **電話会議ライセンスが割り当てられているか、電話会議プロバイダーを Microsoft に変更する場合。**

     このメールには、会議 ID、会議の既定の電話会議電話番号、ユーザーの電話会議 PIN、ユーザーの既存の会議を更新するために使用する Skype for Business Online 会議更新ツールを使用する手順とリンクが含まれます。 「Microsoft [Teams アドオン ライセンスを割り当てる](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 」または [「Microsoft を電話会議プロバイダーとして割り当てる」を参照してください](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)。

    > [!NOTE]
    > 組織で動的電話会議 ID が有効になっている場合、ユーザーがスケジュールするユーザーのすべての会議には、一意の会議 ID が割り当てされます。 組織内で [電話会議の動的な ID を設定できます](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)。 

    このメールの例を次に示します。

     ![Skype for Business の [ライセンスの確認]](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    ライセンスの詳細については、Microsoft Teams のアドオン ライセンス [を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

- **ユーザーの会議 ID または既定の電話会議電話番号が変更されます。**

    このメールには、会議 ID、既定の電話会議の電話番号、ユーザーの既存の会議を更新するために使用する Skype for Business Online 会議更新ツールを使用する手順とリンクが記載されています。 ただし、このメールにはユーザーの電話会議の PIN は含めになっていません。 「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」を参照してください。

    このメールの例を次に示します。

     ![ダイヤルイン会議の情報が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **ユーザーの電話会議の PIN がリセットされます。**

    このメールには、開催者の電話会議 PIN、既存の会議 ID、ユーザーの既定の電話会議電話番号が記載されています。 「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」を参照してください。
    
     このメールの例を次に示します。
    
     ![ダイヤルイン会議の PIN が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **ユーザーのライセンスが削除された場合、または電話会議プロバイダーが Microsoft から他のプロバイダーまたは [なし] に変更された場合。**

    これは、電話会議ライセンス **がユーザー** から削除された場合、または電話会議プロバイダーを [なし] に設定した場合に発生 **します**。

    「 [一ビジネス向け Microsoft 365 のライセンスを割り当てる、または削除する」を参照してください](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。

    このメールの例を次に示します。

     ![ダイヤルイン会議は無効です。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>送信されるメール メッセージを変更する

ユーザーに自動的に送信されるメールを変更できます。 既定では、メールの送信者は Microsoft 365 または Office 365 になりますが、Windows PowerShell を使用して表示名を変更することができます。 詳細については、[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)をご覧ください。

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>メールを送信したくない場合は、どうしますか?

ユーザーへのメールの送信を無効にすると、ユーザーにライセンスが割り当てられた場合でも、メールは送信されません。 この場合、会議 ID、既定の会議電話番号、さらに重要な点として、ユーザーに電話会議の PIN は送信されません。 この場合は、別のメールを送信するか、ユーザーに呼び出すことによってユーザーに通知する必要があります。

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

既定では、メールの送信者は Microsoft 365 または Office 365 から送信されますが、Windows PowerShell を使用してメール アドレスと表示名を変更することができます。 

Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell では、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell で Office 365 を管理するための最善の方法](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Windows PowerShell で Office 365 を管理するための最善の方法](/previous-versions//dn568025(v=technet.10))

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](/powershell/module/teams/?view=teams-ps)」をご覧ください。


## <a name="related-topics"></a>関連トピック

[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)