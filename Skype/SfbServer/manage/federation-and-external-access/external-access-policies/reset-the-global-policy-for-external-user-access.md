---
title: 外部ユーザー アクセスに関するグローバル ポリシーのリセット
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: グローバル ポリシーを完全に削除できない。 グローバル ポリシー **の [削除** ] オプションを使用すると、グローバル ポリシーが既定の設定にリセットされるだけで、外部ユーザー アクセス オプションのサポートは含めされません。
ms.openlocfilehash: e65eb4f2a87789b22654b8de5e3681b1dda47d1a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416560"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>外部ユーザー アクセスのグローバル ポリシーをリセットSkype for Business Server 

使用する必要がなくなった外部ユーザー アクセス ポリシーを作成または構成している場合は、次の方法を使用できます。

  - 作成したサイトやユーザー ポリシーを削除します。

  - グローバル ポリシーを既定の設定にリセットします。 既定のグローバル ポリシー設定では、外部ユーザー アクセスが許可されません。 グローバル ポリシーを削除できない。

グローバル ポリシーを完全に削除できない。 グローバル **ポリシーの** [削除] オプションは、グローバル ポリシーを既定の設定にのみリセットします。外部ユーザー アクセス オプションのサポートは含めされません。

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>グローバル ポリシーを既定の設定にリセットするには

1.  RTCUniversalServerAdmins グループのメンバーであるユーザー アカウント、または同等のユーザー権限を持つユーザー アカウント、または CsAdministrator ロールに割り当てられているユーザー アカウントから、内部展開内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。

4.  [**外部アクセス ポリシー**] タブでグローバル ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。

5.  削除について確認するメッセージが表示されたら、[**OK**] をクリックします。 ページの先頭に、グローバル ポリシーがリセットされたことを知らせるメッセージが表示されます。


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用したグローバル外部アクセス ポリシー Windows PowerShellする

グローバル外部アクセス ポリシーをリセットするには、Windows PowerShellコマンドレットをRemove-CsExternalAccessPolicyします。 このコマンドレットは、管理シェルのSkype for Business Serverリモート セッション から実行Windows PowerShell。 

## <a name="to-reset-the-global-external-access-policy"></a>グローバル外部アクセス ポリシーをリセットするには

  - 次のコマンドは、グローバル外部アクセス ポリシーをリセットします。<br/><br/>Remove-CsExternalAccessPolicy -Identity "global"

詳細については、 [Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) コマンドレットのヘルプ トピックを参照してください。
