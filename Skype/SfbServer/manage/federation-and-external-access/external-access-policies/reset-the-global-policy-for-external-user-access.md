---
title: 外部ユーザー アクセスに関するグローバル ポリシーのリセット
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: グローバル ポリシーを完全に削除することはできません。 グローバル ポリシーに対して [**削除**] オプションを使用すると、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定に、グローバル ポリシーがリセットされるだけです。
ms.openlocfilehash: 824d9f6c924a197a379f668263a23a6df89c27a980c82ea4d13abdd8621968da
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343431"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>外部ユーザー アクセスのグローバル ポリシーをリセットSkype for Business Server 

使用しなくなった外部ユーザー アクセス ポリシーを作成または構成済みの場合は、次の操作を実行できます。

  - 作成したサイトやユーザー ポリシーを削除します。

  - グローバル ポリシーを既定の設定にリセットします。 既定のグローバル ポリシー設定では、外部ユーザー アクセスが許可されません。 グローバル ポリシーは削除できません。

グローバル ポリシーを完全に削除することはできません。 グローバル ポリシーに対して [**削除**] オプションを使用すると、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定に、グローバル ポリシーがリセットされるだけです。

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>グローバル ポリシーを既定の設定にリセットするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。

4.  [**外部アクセス ポリシー**] タブでグローバル ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。

5.  削除について確認するメッセージが表示されたら、[**OK**] をクリックします。 ページの先頭に、グローバル ポリシーがリセットされたことを知らせるメッセージが表示されます。


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用したグローバル外部アクセス ポリシー Windows PowerShellする

グローバル外部アクセス ポリシーをリセットするには、Windows PowerShellコマンドレットをRemove-CsExternalAccessPolicyします。 このコマンドレットは、管理シェルからSkype for Business Serverリモート セッション から実行Windows PowerShell。 

## <a name="to-reset-the-global-external-access-policy"></a>グローバル外部アクセス ポリシーをリセットするには

  - 次のコマンドは、グローバル外部アクセス ポリシーをリセットします。
    
        Remove-CsExternalAccessPolicy -Identity "global"

詳細については [、Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) コマンドレットのヘルプ トピックを参照してください。