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
description: 'Microsoft Teams でダイヤルイン会議の設定が変更されたときに、メールで自動的にユーザーに送信される情報について説明します。 '
ms.openlocfilehash: 1cef5f0ea8865820f6f6f83e29fe5f66799b70ae
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788691"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Microsoft Teams で設定を変更したときにユーザーに送信されるメール

Microsoft を電話会議プロバイダーとして使用する電話 [会議用に有効になっ](set-up-audio-conferencing-in-teams.md) ているユーザーには、メールが自動的に送信されます。

既定では、電話会議が有効になっているユーザーに送信されるメールには4種類のメールが用意されています。 ただし、ユーザーに送信されるメールの数を制限する場合は、オフにすることができます。 Microsoft 365 または Office 365 の電話会議では、次の場合にユーザーのメールにメールが送信されます。

- **電話会議ライセンスが割り当てられているか、電話会議プロバイダーを Microsoft に変更する場合。**

     このメールには、会議 ID、会議用の既定の会議電話番号、ユーザー用の電話会議の PIN、およびユーザーの既存の会議を更新するために使用される Skype for Business Online Meeting Update Tool を使用するための手順とリンクが含まれています。 「 [Microsoft Teams のアドオンライセンスを割り当てる](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 」または「 [microsoft を電話会議プロバイダーとして割り当てる](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)」を参照してください。

    > [!NOTE]
    > 組織で動的会議 Id が有効になっている場合、スケジュールされているすべてのユーザーの会議には、固有の会議 Id が割り当てられます。 [組織内の電話会議の動的 id](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)を設定することができます。 

    このメールの例を次に示します。

     ![Skype for Business のライセンスを確認する](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    ライセンスの詳細については、「 [Microsoft Teams のアドオンライセンス](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)」を参照してください。

- **会議 ID またはユーザーの既定の会議の電話番号が変更されます。**

    このメールには、会議 ID、既定の会議電話番号、およびユーザーの既存の会議を更新するために使用される Skype for Business Online Meeting 更新ツールを使用するための手順とリンクが含まれています。 ただし、このメールには、ユーザーの電話会議の PIN は含まれていません。 「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user-in-teams.md)」を参照してください。

    このメールの例を次に示します。

     ![ダイヤルイン会議情報が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **ユーザーの電話会議の PIN がリセットされます。**

    このメールには、開催者の電話会議の PIN、既存の会議 ID、ユーザー用の既定の会議電話番号が含まれています。 「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin-in-teams.md)」を参照してください。
    
     このメールの例を次に示します。
    
     ![ダイヤルイン会議の PIN が変更されました。](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **ユーザーのライセンスが削除されるか、電話会議プロバイダーが Microsoft から別のプロバイダーまたは [なし] に変更されたとき。**

    この問題は、電話 **会議** のライセンスがユーザーから削除された場合、または電話会議プロバイダーを **[なし**] に設定した場合に発生します。

    「 [Microsoft 365 for business のライセンスの割り当てまたは削除」を](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)参照してください。

    このメールの例を次に示します。

     ![ダイヤルイン会議が無効になっています。](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>送信されたメールメッセージに変更を加える

ユーザーに自動的に送信されるメールに変更を加えることができます。 既定では、メールの送信者は Microsoft 365 または Office 365 から送信されますが、Windows PowerShell を使用して表示名を変更することができます。 詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>メールを送信したくない場合はどうすればよいですか?

ユーザーへのメールの送信を無効にすると、ユーザーにライセンスが割り当てられてもメールは送信されません。 この場合、会議 ID、既定の会議電話番号、さらに重要なのは、電話会議の PIN はユーザーに送信されません。 この問題が発生した場合は、個別のメールを送信するか、または電話をかけて、ユーザーに通知する必要があります。

既定では、メールはユーザーに送信されますが、電話会議のメールを受信しないようにするには、Microsoft Teams または Windows PowerShell を使用します。 

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジの設定**] ペインで、[**ダイヤルイン設定が変わると、ユーザーに自動的に電子メールが送信されます**] を有効または無効にします。

4. **[保存]** をクリックします。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Windows PowerShell を使用する**

詳細については、[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)をご覧ください。


## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

既定では、メールの送信者は、Microsoft 365 または Office 365 から送信されますが、Windows PowerShell を使用して、メールアドレスと表示名を変更することができます。 

Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Microsoft 365 または Office 365 を管理し、日常業務を簡素化することができます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)

Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。


## <a name="related-topics"></a>関連トピック

[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
