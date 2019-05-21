---
title: Skype for Business Server で PIN ポリシーを削除する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: '概要: Skype for Business Server のユーザーのダイヤルイン会議の PIN を削除します。'
ms.openlocfilehash: 2f42531480ac4099d574a21a96f1954abc70d1d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283782"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>Skype for Business Server で PIN ポリシーを削除する
 
**概要:** Skype for Business Server のユーザーのダイヤルイン会議の PIN を削除します。
  
暗証番号 (PIN) ポリシーを削除するには、次の手順を実行します。
  
> [!NOTE]
> グローバル PIN ポリシーを削除することはできません。 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルで PIN ポリシーを削除するには

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。
    
4. [**PIN ポリシー**] ページの検索フィールドに、削除するポリシーの名前または名前の一部を入力します。
    
5. ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
6. [**OK**] をクリックします。
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して PIN ポリシーを削除する

PIN ポリシーを削除するには、Windows PowerShell と CsPinPolicy コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。 リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
### <a name="to-remove-a-specific-pin-policy"></a>特定の PIN ポリシーを削除するには

- 次のコマンドは、Identity が RedmondPinPolicy の PIN ポリシーを削除します。
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>サイト スコープに適用されていたすべての PIN ポリシーを削除するには

- 次のコマンドは、サイト スコープで構成されたすべての PIN ポリシーを削除します。
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>共通パターンの使用を許可するすべての PIN ポリシーを削除するには

- 次のコマンドは、共通パターン G の使用を許可するすべての PIN ポリシーを削除します。
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

詳細については、 [CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)コマンドレットのヘルプトピックを参照してください。
  

