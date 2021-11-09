---
title: '[PIN ポリシーを削除する] Skype for Business Server'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: '概要: ユーザーのダイヤルイン会議用の PIN を削除Skype for Business Server。'
ms.openlocfilehash: 61bd6aabf823ab73f26832b1494bf625d3ea641c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847430"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>[PIN ポリシーを削除する] Skype for Business Server
 
**概要:** ユーザーのダイヤルイン会議 PIN を削除して、Skype for Business Server。
  
暗証番号 (PIN) ポリシーを削除するには、次の手順を実行します。
  
> [!NOTE]
> グローバル PIN ポリシーを削除することはできません。 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>[コントロール パネル] で PIN Skype for Business Server削除するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。
    
4. [**PIN ポリシー**] ページの検索フィールドにで、削除するポリシーの名前または名前の一部を入力します。
    
5. ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
6. **[OK]** をクリックします。
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した PIN ポリシー Windows PowerShell削除する

PIN ポリシーを削除するには、pin ポリシーと Windows PowerShellコマンドレットをRemove-CsPinPolicyします。 このコマンドレットは、管理者管理シェルSkype for Business Serverリモート セッションから実行Windows PowerShell。 リモート サーバーを使用してサーバー Windows PowerShellする方法[Skype for Business Server、Microsoft Lync リモート PowerShell 管理を参照してください](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 このプロセスは、同じSkype for Business Server。
  
### <a name="to-remove-a-specific-pin-policy"></a>特定の PIN ポリシーを削除するには

- 次のコマンドは、Identity が RedmondPinPolicy の PIN ポリシーを削除します。
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>サイト スコープに適用されているすべての PIN ポリシーを削除するには

- 次のコマンドは、サイト スコープで構成されたすべての PIN ポリシーを削除します。
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>一般的なパターンを使用できるすべての PIN ポリシーを削除するには

- 次のコマンドは、共通パターン G の使用を許可するすべての PIN ポリシーを削除します。
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

詳細については [、Remove-CsPinPolicy コマンドレットのヘルプ トピックを参照](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) してください。
