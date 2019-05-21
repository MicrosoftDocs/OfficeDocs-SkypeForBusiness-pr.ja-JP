---
title: Skype for Business Server で PIN ポリシー情報を表示する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: '概要: Skype for Business Server のユーザーの PIN ポリシー情報を表示します。'
ms.openlocfilehash: 5f6269b766748d5027c0a8182dd027754cd5cc00
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297590"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Skype for Business Server で PIN ポリシー情報を表示する
 
**概要:** Skype for Business Server のユーザーの PIN ポリシー情報を表示します。
  
[ **Pin ポリシー** ] タブを使用して、IP 電話を使って Skype for business に接続しているユーザーの暗証番号 (pin) の認証を確認できます。 PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。
  
ユーザー レベルまたはサイト レベルの PIN ポリシーを変更するには、次の手順に従います。 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルの PIN ポリシーに関する情報を表示するには

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Skype for Business Server を展開したネットワーク内のコンピューターにログオンします。.
    
2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。
    
4. [**PIN ポリシー**] ページでポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した PIN ポリシーの表示

Windows PowerShell と CsPinPolicy コマンドレットを使用して、PIN ポリシーを表示することもできます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。
  
### <a name="to-view-pin-policies"></a>PIN ポリシーを表示するには

すべての PIN ポリシーに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。
    
  ```
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

詳細については、 [CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)コマンドレットのヘルプトピックを参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server で新しい PIN ポリシーを作成する](create-a-new-pin-policy.md)
