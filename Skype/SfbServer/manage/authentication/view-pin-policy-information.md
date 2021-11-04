---
title: '[PIN ポリシー情報の表示] Skype for Business Server'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: '概要: ユーザーの PIN ポリシー情報を表示するSkype for Business Server。'
ms.openlocfilehash: 112eebb72ed1599ca85031653651bcaa1dad41e1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765525"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>[PIN ポリシー情報の表示] Skype for Business Server
 
**概要:** ユーザーの PIN ポリシー情報を表示Skype for Business Server。
  
[PIN ポリシー]**タブを使用** して、IP Phone を使用してユーザーに接続しているユーザーの個人識別番号 (PIN) Skype for Business表示できます。 PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。
  
ユーザー レベルまたはサイト レベルの PIN ポリシーを変更するには、次の手順に従います。 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>コントロール パネルで PIN ポリシーに関する情報Skype for Business Server表示するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。
    
4. [**PIN ポリシー**] ページでポリシーをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>コマンドレットを使用した PIN ポリシー Windows PowerShellする

また、PIN ポリシーを表示するには、Windows PowerShellコマンドレットをGet-CsPinPolicyします。 このコマンドレットは、管理シェルから、またはSkype for Business Serverのリモート セッションから実行Windows PowerShell。 リモート サーバーを使用してサーバー Windows PowerShellする方法[Skype for Business Server、Microsoft Lync リモート PowerShell 管理を参照してください](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 このプロセスは、同じSkype for Business Server。
  
### <a name="to-view-pin-policies"></a>PIN ポリシーを表示するには

すべての PIN ポリシーに関する情報を表示するには、次のコマンドを [管理シェル] Skype for Business Server入力し、Enter キーを押します。
    
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

詳細については [、Get-CsPinPolicy コマンドレットのヘルプ トピックを参照](/powershell/module/skype/get-cspinpolicy?view=skype-ps) してください。
  
## <a name="see-also"></a>関連項目

[新しい PIN ポリシーを作成Skype for Business Server](create-a-new-pin-policy.md)