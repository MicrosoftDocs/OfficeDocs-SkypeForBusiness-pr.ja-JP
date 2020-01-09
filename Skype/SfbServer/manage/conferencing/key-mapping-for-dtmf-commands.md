---
title: Skype for Business Server の DTMF コマンドのキーマッピングを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: '概要: Skype for Business Server のデュアルトーンマルチ周波数 (DTMF) コマンドのキーマッピングを管理する方法について説明します。'
ms.openlocfilehash: 3bab799bb116d0ded48002eb91898ffc1587543c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991822"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>Skype for Business Server の DTMF コマンドのキーマッピングを管理する
 
**概要:** Skype for Business Server のデュアルトーンマルチ周波数 (DTMF) コマンドのキーマッピングを管理する方法について説明します。
  
ダイヤルイン会議のユーザーは、電話キーパッドのキーを押して、デュアルトーン多重周波数 (DTMF) のコマンドを実行できます。DTMF コマンドを使用すると、会議にダイヤルインするユーザーは、電話のキーパッドを使用して会議設定 (自身をミュートおよびミュート解除したり、会議をロックおよびロック解除したりするなど) を制御できます。 
  
DTMF コマンドに使用されるキーを管理するには、 **CsDialinConferencingDtmfConfiguration**、 **CsDialinConferencingDtmfConfiguration**、および**New CsDialinConferencingDtmfConfiguration**コマンドレットを使用して、Skype for business Server 管理シェルを使用します。
  
サイトの新たな DTMF 設定を作成すると、そのサイト設定はグローバル設定よりも優先されるようになります。 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>DTMF コマンドのキー マッピングを管理する

1. コンピューターに RTCUniversalServerAdmins グループのメンバーとしてログオンするか、Cs-ServerAdministrator または CsAdministrator 役割のメンバーとしてログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. ダイヤイン会議に使用される DTMF 設定を表示するには、コマンド プロンプトで次のコマンドを実行します。
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. ダイヤイン会議に使用される DTMF 設定を変更するには、次のコマンドレットを実行し、変更対象である各オプションで押されるキーを指定します。
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (オプション) 特定サイトに対する DTMF コマンドの追加セットを作成するには、サイト ID と **New-CsDialinConferencingDtmfConfiguration** コマンドレットを使用します。
    
次の例では、アナウンスを有効/無効にするために押されるキーと、全参加者のミュート/ミュート解除のために押されるキーを交換します。ID が指定されていないため、これらの変更はグローバル DTMF 設定に適用されます。
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

詳細については、「 [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps)、 [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)、 [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)」を参照してください。
  

