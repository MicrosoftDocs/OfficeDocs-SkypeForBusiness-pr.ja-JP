---
title: ビジネス サーバーの Skype の暗証番号 (pin) ポリシーを削除します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: '概要: は、Skype のビジネス サーバーのユーザーのダイヤルイン会議の PIN を削除します。'
ms.openlocfilehash: b281716c2e0560936ea2f94b773c8191f3e8987e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919648"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a>ビジネス サーバーの Skype の暗証番号 (pin) ポリシーを削除します。
 
**の概要:** Skype のビジネス サーバーのユーザーのダイヤルイン会議の PIN を削除します。
  
暗証番号 (PIN) ポリシーを削除するには、次の手順を実行します。
  
> [!NOTE]
> グローバル PIN ポリシーを削除することはできません。 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype の暗証番号 (pin) ポリシーを削除するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。
    
4. [**PIN ポリシー**] ページの検索フィールドに、削除するポリシーの名前または名前の一部を入力します。
    
5. ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。
    
6. [**OK**] をクリックします。
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、暗証番号 (pin) ポリシーを削除します。

暗証番号 (pin) ポリシーを削除するには、Windows PowerShell と削除 CsPinPolicy コマンドレットを使用します。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
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

詳細については、[削除 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  

