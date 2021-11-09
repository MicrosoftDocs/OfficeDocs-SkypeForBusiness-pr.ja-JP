---
title: '[ユーザーの通話パークを有効にする] Skype for Business'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: '[ユーザーがユーザーに通話パークを有効にする] Skype for Business Server エンタープライズ VoIP。'
ms.openlocfilehash: 87ac29c8f9b6c893149db8fb91561ee4b3cf1166
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843510"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>[ユーザーの通話パークを有効にする] Skype for Business
 
[ユーザーがユーザーに通話パークを有効にする] Skype for Business Server エンタープライズ VoIP。
  
既定では、通話パークは、すべてのユーザーに対して無効になっています。 ユーザーは、音声ポリシーで通話パークを有効にするまで、通話をパークしたり、パークされた通話を取得したりすることはできません。
  
コール パークは、グローバル スコープまたはサイト スコープまたはユーザー スコープで有効にできます。 ユーザー スコープはサイト スコープよりも優先され、サイト スコープはグローバル スコープよりも優先されます。 複数の音声ポリシーがある場合は、グローバル ポリシーではなく、すべてのポリシーを確認してコール パークを有効にしてください。
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>コントロール パネルSkype for Business Serverを使用してユーザーの通話パークを有効にするには

1. **RTCUniversalServerAdmins** グループのメンバーとして、または **CsVoiceAdministrator 、CsServerAdministrator、** または **CsAdministrator** 管理役割のメンバーとしてコンピューターにログオンします。
    
2. [コントロール Skype for Business Server] を開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [音声ポリシー **] タブをクリック** します。
    
5. 既存の音声ポリシーをダブルクリックして、[音声ポリシーの編集 **] ダイアログ ボックスを** 開きます。
    
6. [通話 **機能] で、[** 通話 **パークを有効にする] を選択します**。
    
7. **[OK] を** クリックして音声ポリシーを保存する
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>コマンドレットを使用してユーザーの通話パークを有効にするには

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator 管理役割のメンバーとしてコンピューターにログオンします。
    
2. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
3. 次を実行します: 
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    たとえば、既定のグローバル音声ポリシーでコール パークを有効にするには、次の方法を実行します。
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>関連項目



[音声ポリシーを作成または変更し、音声ポリシーで PSTN 使用法レコードを構成Skype for Business](voice-policy-and-pstn-usage-records.md)

