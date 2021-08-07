---
title: DTMF コマンドのキー マッピングを管理Skype for Business Server
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
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: '概要: デュアルトーンマルチ周波数 (DTMF) コマンドのキー マッピングを管理する方法について説明します。Skype for Business Server。'
ms.openlocfilehash: 106cd301826792ec494df4d490a6b953baf3badd1740d9cfd2de12e6de966d09
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276852"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a>DTMF コマンドのキー マッピングを管理Skype for Business Server
 
**概要:** デュアルトーンマルチ周波数 (DTMF) コマンドのキー マッピングを管理する方法については、Skype for Business Server。
  
ダイヤルイン会議のユーザーは、電話キーパッドのキーを押して、デュアルトーン多重周波数 (DTMF) のコマンドを実行できます。 DTMF コマンドを使用すると、会議にダイヤルインするユーザーは、電話のキーパッドを使用して会議設定 (自身をミュートおよびミュート解除したり、会議をロックおよびロック解除したりするなど) を制御できます。 
  
DTMF コマンドに使用するキーを管理するには **、Get-CsDialinConferencingDtmfConfiguration、Set-CsDialinConferencingDtmfConfiguration、****および New-CsDialinConferencingDtmfConfiguration** コマンドレットを使用して Skype for Business Server 管理シェルを使用します。 
  
サイトの新たな DTMF 設定を作成すると、そのサイト設定はグローバル設定よりも優先されるようになります。 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a>DTMF コマンドのキー マッピングを管理する

1. RTCUniversalServerAdmins グループのメンバーか、Cs-ServerAdministrator または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。
    
2. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
3. ダイヤルイン会議に使用される DTMF 設定を表示するには、コマンド プロンプトで次のコマンドを実行します。
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. ダイヤルイン会議に使用される DTMF 設定を変更するには、次のコマンドレットを実行し、変更する各オプションに対して押すキーを指定します。
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. (オプション) 特定サイトに対する DTMF コマンドの追加セットを作成するには、サイト ID と **New-CsDialinConferencingDtmfConfiguration** コマンドレットを使用します。
    
次の使用例は、押されたキーを入れ替え、アナウンスを有効または無効にし、すべての参加者をミュートおよびミュート解除するために押されたキーを交換します。 Identity が指定されていないので、これらの変更はグローバル DTMF 設定に適用されます。
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

詳細については[、「Get-CsDialInConferencingDtmfConfiguration、Set-CsDialInConferencingDtmfConfiguration、](/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps)[および New-CsDialInConferencingDtmfConfiguration」](/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)を参照してください。 [](/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)
