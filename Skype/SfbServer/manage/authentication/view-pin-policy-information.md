---
title: Skype for Business Server で PIN ポリシー情報を表示する
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
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: '概要: Skype for Business Server のユーザーの PIN ポリシー情報を表示します。'
ms.openlocfilehash: 4c223d5736df7f5f8ee1dbee11401a9fef2237cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806527"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Skype for Business Server で PIN ポリシー情報を表示する
 
**概要:** Skype for Business Server のユーザーの PIN ポリシー情報を表示します。
  
[PIN ポリシー] **タブを使用** して、IP 電話で Skype for Business に接続しているユーザーの暗証番号 (PIN) 認証を表示できます。 PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。
  
ユーザー レベルまたはサイト レベルの PIN ポリシーを変更するには、次の手順に従います。 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルで PIN ポリシーに関する情報を表示するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。
    
4. [**PIN ポリシー**] ページでポリシーをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用して PIN Windows PowerShell表示する

また、PIN ポリシーを表示するには、Windows PowerShellコマンドレットをGet-CsPinPolicyします。 このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 プロセスは Skype for Business Server でも同じです。
  
### <a name="to-view-pin-policies"></a>PIN ポリシーを表示するには

すべての PIN ポリシーに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、Enter キーを押します。
    
  ```PowerShell
  Get-CsPinPolicy
  ```

次のような情報が表示されます。

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

詳細については [、Get-CsPinPolicy コマンドレットのヘルプ トピックを参照](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server で新しい PIN ポリシーを作成する](create-a-new-pin-policy.md)
