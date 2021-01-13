---
title: Skype for Business でユーザーのコール パークを有効にする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Skype for Business Server のコール パークに対してユーザーを有効エンタープライズ VoIP。
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830957"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Skype for Business でユーザーのコール パークを有効にする
 
Skype for Business Server のコール パークに対してユーザーを有効エンタープライズ VoIP。
  
既定では、コール パークはすべてのユーザーに対して無効になっています。 ユーザーは、音声ポリシーでコール パークが有効になるまで、通話をパークしたり、パークされた通話を取得したりすることはできません。
  
コール パークは、グローバル スコープまたはサイト スコープまたはユーザー スコープで有効にできます。 ユーザー スコープはサイト スコープより優先され、サイト スコープはグローバル スコープよりも優先されます。 複数の音声ポリシーがある場合は、グローバル ポリシーではなく、すべてのポリシーを確認してコール パークを有効にしてください。
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Skype for Business Server コントロール パネルを使用してユーザーのコール パークを有効にするには

1. **RTCUniversalServerAdmins** グループのメンバーとして、または **CsVoiceAdministrator、CsServerAdministrator、****または****CsAdministrator** 管理役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server コントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [音声ポリシー **] タブをクリック** します。
    
5. 既存の音声ポリシーをダブルクリックして、[音声ポリシーの編集 **] ダイアログ ボックスを** 開きます。
    
6. [通話 **機能] で、[** コール パーク **を有効にする] を選択します**。
    
7. **[OK] を** クリックして音声ポリシーを保存する
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>コマンドレットを使用してユーザーのコール パークを有効にするには

1. RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator 管理者役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。
    
3. 次のコマンドを実行します。
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    たとえば、既定のグローバル音声ポリシーに対してコール パークを有効にするには、
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>関連項目



[音声ポリシーを作成または変更し、Skype for Business で PSTN 使用法レコードを構成する](voice-policy-and-pstn-usage-records.md)

