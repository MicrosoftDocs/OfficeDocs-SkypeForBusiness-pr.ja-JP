---
title: Skype のビジネス サーバーの暗証番号 (pin) ポリシー情報を表示します。
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: '概要: ビジネス サーバーの Skype のユーザーの暗証番号 (pin) ポリシー情報を表示します。'
ms.openlocfilehash: 5fdd042f01c325bfffedbfa32fa14d9e667ef7be
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222857"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Skype のビジネス サーバーの暗証番号 (pin) ポリシー情報を表示します。
 
**の概要:** ビジネス サーバーの Skype のユーザーの暗証番号 (pin) ポリシー情報を表示します。
  
ビュー個人識別番号 (PIN) 認証の IP 電話でのビジネス用の Skype に接続しているユーザーに**暗証番号 (pin) ポリシー** ] タブを使用することができます。 PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。
  
ユーザー レベルまたはサイト レベルの PIN ポリシーを変更するには、次の手順に従います。 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Skype のビジネス サーバーのコントロール パネルの暗証番号 (pin) のポリシーに関する情報を表示するのには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。
    
4. [**PIN ポリシー**] ページでポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して、暗証番号 (pin) ポリシーを表示します。

Windows PowerShell と Get CsPinPolicy コマンドレットを使用して、暗証番号 (pin) ポリシーを表示することもできます。 ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-view-pin-policies"></a>PIN ポリシーを表示するには

すべての PIN ポリシーに関する情報を表示するのには、Skype のビジネス サーバー管理シェルの次のコマンドを入力し、し、ENTER キーを押します。
    
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

詳細については、 [Get CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  
## <a name="see-also"></a>関連項目

[Skype のビジネス サーバーの新しい暗証番号 (pin) ポリシーを作成します。](create-a-new-pin-policy.md)
