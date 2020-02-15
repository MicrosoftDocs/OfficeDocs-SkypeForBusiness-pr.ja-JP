---
title: 外部ユーザーアクセスに関するグローバルポリシーのリセット
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: グローバル ポリシーを完全に削除することはできません。 グローバル ポリシーに対して [**削除**] オプションを使用すると、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定に、グローバル ポリシーがリセットされるだけです。
ms.openlocfilehash: acb275ac924dbb5b7e9ad377ab4d287a0734f752
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043659"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Skype for Business Server での外部ユーザーアクセスに関するグローバルポリシーのリセット 

使用しなくなった外部ユーザー アクセス ポリシーを作成または構成済みの場合は、次の操作を実行できます。

  - 作成したサイトやユーザー ポリシーを削除します。

  - グローバル ポリシーを既定の設定にリセットします。 既定のグローバル ポリシー設定では、外部ユーザー アクセスが許可されません。 グローバル ポリシーは削除できません。

グローバル ポリシーを完全に削除することはできません。 グローバル ポリシーに対して [**削除**] オプションを使用すると、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定に、グローバル ポリシーがリセットされるだけです。

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>グローバル ポリシーを既定の設定にリセットするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。

4.  [**外部アクセス ポリシー**] タブでグローバル ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。

5.  削除について確認するメッセージが表示されたら、[**OK**] をクリックします。 ページの先頭に、グローバル ポリシーがリセットされたことを知らせるメッセージが表示されます。


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してグローバル外部アクセスポリシーをリセットする

グローバル外部アクセスポリシーは、Windows PowerShell と Get-csexternalaccesspolicy コマンドレットを使用してリセットできます。 このコマンドレットは、Skype for Business Server 管理シェルまたはリモートセッション Windows PowerShell から実行できます。 

## <a name="to-reset-the-global-external-access-policy"></a>グローバル外部アクセスポリシーをリセットするには

  - 次のコマンドは、グローバル外部アクセス ポリシーをリセットします。
    
        Remove-CsExternalAccessPolicy -Identity "global"

詳細については、 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。


