---
title: 外部ユーザー アクセスに関するグローバル ポリシーのリセット
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: グローバル ポリシーを完全に削除することはできません。 外部ユーザー アクセス オプションのサポートが含まれていない既定の設定をグローバル ポリシーをリセットすることがのみグローバル ポリシーを**削除**する] オプションを使用します。
ms.openlocfilehash: 048d1f1aabd2e188cefa25358068ea6ec150b8f3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197626"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>ビジネス サーバーの Skype での外部ユーザー アクセスのグローバル ポリシーをリセットします。 

作成または、外部ユーザー アクセス ポリシーを使用する必要がなくなったように構成した場合は、次の操作を行うことができます。

  - 作成したサイトまたはユーザーのポリシーを削除します。

  - グローバル ポリシーを既定の設定にリセットします。 既定のグローバル ポリシー設定は、すべての外部ユーザー アクセスを拒否します。 グローバル ポリシーは削除できません。

グローバル ポリシーを完全に削除することはできません。 外部ユーザー アクセス オプションのサポートが含まれていない既定の設定をグローバル ポリシーをリセットすることがのみグローバル ポリシーを**削除**する] オプションを使用します。

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>グローバル ポリシーを既定の設定にリセットするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。

3.  左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックして、[**外部アクセス ポリシー**] をクリックします。

4.  [**外部アクセス ポリシー** ] タブで、[グローバル ポリシー] をクリック**を編集**する、し、[**削除**] をクリックします。

5.  削除の確認メッセージが表示されたら、[ **OK**を] をクリックします。 グローバル ポリシーがリセットされたことを通知するページの上部にあるメッセージが表示されます。


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、グローバル外部アクセス ポリシーをリセットします。

グローバル外部アクセス ポリシーは、Windows PowerShell と削除 CsExternalAccessPolicy コマンドレットを使用してリセットできます。 ビジネス サーバー管理シェルの Skype から、または Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 

## <a name="to-reset-the-global-external-access-policy"></a>グローバル外部アクセス ポリシーをリセットするのには

  - このコマンドは、グローバル外部アクセス ポリシーをリセットします。
    
        Remove-CsExternalAccessPolicy -Identity "global"

詳細については、[削除 CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプ トピックを参照してください。


