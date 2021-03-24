---
title: Skype for Business Server で PIN ポリシーを削除する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: '概要: Skype for Business Server のユーザーのダイヤルイン会議 PIN を削除します。'
ms.openlocfilehash: b85d2bb29f8a1a28279a59f72957d201886d1dc4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096793"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Skype for Business Server で PIN ポリシーを削除する
 
**概要:** Skype for Business Server のユーザーのダイヤルイン会議 PIN を削除します。
  
暗証番号 (PIN) ポリシーを削除するには、次の手順を実行します。
  
> [!NOTE]
> グローバル PIN ポリシーを削除することはできません。 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルで PIN ポリシーを削除するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。
    
4. [**PIN ポリシー**] ページの検索フィールドにで、削除するポリシーの名前または名前の一部を入力します。
    
5. ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
6. **[OK]** をクリックします。
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した PIN ポリシー Windows PowerShellする

PIN ポリシーを削除するには、pin ポリシーと Windows PowerShellコマンドレットをRemove-CsPinPolicyします。 このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
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
