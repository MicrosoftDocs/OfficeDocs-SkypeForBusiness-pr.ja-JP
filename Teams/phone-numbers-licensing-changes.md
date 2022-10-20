---
title: 電話番号とライセンスの変更
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
description: ライセンスの変更が電話番号管理に与える影響について説明します。
ms.openlocfilehash: e023c1606157a5beeafedfa358e470555ba7f653
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614320"
---
# <a name="how-licensing-affects-phone-number-management"></a>ライセンスが電話番号管理に与える影響

ユーザーにライセンスを削除して割り当てる方法は、Microsoft Teams で公衆交換電話網 (PSTN) 通話を行って受信するユーザーの機能に影響を与える可能性があります。 この記事では、ユーザーが PSTN 通話を行って受信する機能に影響を与えないように、ライセンス変更を管理する方法について説明します。

電話番号の管理の一般的な情報については、「 [組織の電話番号を管理する」を参照してください](manage-phone-numbers-landing-page.md)。 Teams アドオン ライセンスの一般的な情報については、「 [Microsoft Teams アドオン ライセンス」を](/teams-add-on-licensing/microsoft-teams-add-on-licensing.md)参照してください。



## <a name="remove-a-license"></a>ライセンスを削除する

電話番号が割り当てられているユーザーがいて、1 つ以上の前提条件ライセンスを削除した場合、ライセンスを削除すると、ユーザーから電話番号が割り当て解除されます。 電話番号が割り当てられていないと、Microsoft Teams で PSTN 通話を行って受信するユーザーの機能に影響があります。

ユーザーの [PSTN 接続オプション](pstn-connectivity.md)に応じて、ライセンスを削除すると、テレフォニー パラメーターに次の影響が及びます。

- **通話プランの電話番号を持つユーザーから Microsoft 365 通話プラン ライセンスを削除すると、** 次のようになります。
  - OnPremLineUri の任意の値を LineUri にコピーする
  - EnterpriseVoiceEnabled を False に設定する
  - 電話番号データベースで電話番号の割り当て状態を [未割り当て] に設定する


- **オペレーター接続電話番号を持つユーザーから Microsoft 365 Phone System ライセンスを削除** すると、次のようになります。
  - Clear LineUri
  - EnterpriseVoiceEnabled を False に設定する
  - 電話番号データベースで電話番号の割り当て状態を [未割り当て] に設定する


- **ダイレクト ルーティング電話番号を持つユーザーから Microsoft 365 Phone System ライセンスを削除すると、** 次のようになります。
  - Clear LineUri
  - EnterpriseVoiceEnabled を False に設定する
  - 電話番号データベースから電話番号を削除する


## <a name="change-a-license"></a>ライセンスを変更する

前提条件のライセンスの 1 つを含むユーザーのライセンスを変更する必要がある場合は、ライセンスの変更が同時に行われ、保存されるようにする必要があります。 この方法により、ユーザーは割り当てられた電話番号を保持し、Microsoft Teams で PSTN 通話の発信と受信を続行できます。 

たとえば、現在Microsoft 365 E3 ライセンスを持っているユーザーにMicrosoft 365 E5 ライセンスを割り当てるとします。 

- Teams 管理センターを使用している場合は、ユーザーの詳細の [ **ライセンスとアプリ** ] タブで、[ **変更の保存]** をクリックする前に、古いライセンスが削除され、新しいライセンスが追加されていることを確認します。 

- PowerShell コマンドレット [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) または [Set-MgUserLicense](/powershell/module/microsoft.graph.users.actions/set-mguserlicense) を使用している場合は、コマンドレットを 1 回実行し、-AddLicenses パラメーターと -RemoveLicenses パラメーターの両方を使用します。

(古いライセンスを削除して変更を保存し、新しいライセンスを追加して変更を保存した場合、電話番号は割り当て解除され、ユーザーは Microsoft Teams で PSTN 通話を行って受信できなくなる可能性があります。 新しいライセンスを割り当てた後、電話番号をユーザーに再割り当てる必要があります)。










