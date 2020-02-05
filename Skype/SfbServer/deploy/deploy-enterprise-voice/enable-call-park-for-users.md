---
title: Skype for Business のユーザーに対してコールパークを有効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business Server Enterprise Voice でのコールパークのユーザーを有効にします。
ms.openlocfilehash: 6642af2a7af698a1127ff2a9bb4e45df73d18c50
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767280"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Skype for Business のユーザーに対してコールパークを有効にする
 
Skype for Business Server Enterprise Voice でのコールパークのユーザーを有効にします。
  
既定では、すべてのユーザーに対して [コールパーク] が無効になっています。 ユーザーは、音声ポリシーでのコールパークが有効になるまで、通話をパークしたり、保留中の通話を取得したりすることはできません。
  
グローバルスコープまたはサイトのスコープまたはユーザーの範囲で、通話パークを有効にすることができます。 ユーザー スコープはサイト スコープより優先され、サイト スコープはグローバル スコープよりも優先されます。 複数のボイスポリシーがある場合は、グローバルポリシーだけでなく、すべてのポリシーを確認してコールパークを有効にします。
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Skype for Business Server コントロールパネルを使用して、ユーザーに対してコールパークを有効にするには

1. **RTCUniversalServerAdmins** グループのメンバーとしてコンピューターにログオンするか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** 管理者役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server コントロールパネルを開きます。
    
3. 左側のナビゲーション バーで [**音声ルーティング**] をクリックします。
    
4. [**音声ポリシー**] タブをクリックします。
    
5. 既存の音声ポリシーをダブルクリックして、[**音声ポリシーの編集**] ダイアログ ボックスを開きます。
    
6. [**通話機能**] の [**コール パークを有効にする**] を選択します。
    
7. [**OK**] をクリックして音声ポリシーを保存します。
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>コマンドレットを使用してユーザーのコールパークを有効にするには

1. RTCUniversalServerAdmins グループのメンバーとしてコンピューターにログオンするか、CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator 管理者役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. 次のコマンドレットを実行します。
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    たとえば、既定のグローバルボイスポリシーのコールパークを有効にするには、次のようにします。
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>関連項目



[Skype for Business で音声ポリシーを作成または変更し、PSTN 使用状況レコードを構成する](voice-policy-and-pstn-usage-records.md)

