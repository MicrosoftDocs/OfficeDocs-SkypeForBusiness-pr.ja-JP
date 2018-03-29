---
title: Skype for Business 2015 でのユーザーに対するコール パークの有効化
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: ビジネス サーバーのエンタープライズ VoIP のユーザーが Skype のコール パークを有効にします。
ms.openlocfilehash: 3af13e59541799a75c58f6e796bf07e7a978065e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-park-for-users-in-skype-for-business-2015"></a>Skype for Business 2015 でのユーザーに対するコール パークの有効化
 
ビジネス サーバーのエンタープライズ VoIP のユーザーが Skype のコール パークを有効にします。
  
既定では、すべてのユーザーに対してコール パークが無効になります。 ユーザーが呼び出しを駐車または音声ポリシーでコール パークの有効になるまで停止の呼び出しを取得できません。
  
グローバル スコープまたはサイト スコープまたはユーザー スコープで、コール パークを有効にできます。 ユーザー スコープはサイト スコープより優先され、サイト スコープはグローバル スコープよりも優先されます。 複数のボイス ポリシーがある場合は、コール パーク、グローバル ポリシーだけではなくを有効にするすべてのポリシーを確認します。
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>ユーザーに対してコール パークを有効にするビジネス サーバーのコントロール パネルの Skype を使用するには

1. **RTCUniversalServerAdmins** グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。
    
2. Skype をビジネス サーバーのコントロール パネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [**音声ポリシー**] タブをクリックします。
    
5. 既存の音声ポリシーをダブルクリックして、[**音声ポリシーの編集**] ダイアログ ボックスを開きます。
    
6. [**通話機能**] の [**コール パークを有効にする**] を選択します。
    
7. [**OK**] をクリックして音声ポリシーを保存します。
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>ユーザーのコール パークを有効にするコマンドレットを使用するには

1. RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator 管理者役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. 次のコマンドレットを実行します。
    
   ```
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    たとえば、既定のグローバル音声ポリシーのコール パークを有効にします。
    
   ```
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>関連項目

#### 

[作成し、音声ポリシーを変更またはビジネス 2015年の Skype の PSTN 使用法レコードを構成します。](voice-policy-and-pstn-usage-records.md)

