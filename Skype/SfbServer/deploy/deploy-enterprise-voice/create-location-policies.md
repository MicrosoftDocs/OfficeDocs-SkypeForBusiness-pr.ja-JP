---
title: Skype for Business Server で場所ポリシーを作成する
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
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Skype for Business Server エンタープライズ VoIP で拡張緊急サービス (E9-1-1) の場所ポリシーを構成する方法については、このトピックを参照エンタープライズ VoIP。
ms.openlocfilehash: cee02204a9c5b3708a83e9433f6a88c70230fd64
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093145"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>Skype for Business Server で場所ポリシーを作成する

Skype for Business Server エンタープライズ VoIP で拡張緊急サービス (E9-1-1) の場所ポリシーを構成する方法については、このトピックを参照エンタープライズ VoIP。 

Skype for Business Server は、場所ポリシーを使用して、クライアント登録中に Skype for Business クライアントを E9-1-1 で有効にします。 場所のポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。 詳細については [、「Plan location policis for Skype for Business Server」を参照してください](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。

場所ポリシーは、Skype for Business コントロール パネルを使用するか [、New-CsLocationPolicy コマンドレットを使用して定義](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) します。

> [!NOTE]
> Skype for Business Server では、クライアントの複数の緊急電話番号の構成がサポートされます。 複数の緊急電話番号を構成する場合は [、「Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) で複数の緊急電話番号を計画する」および「Skype for Business で複数の緊急電話番号を構成する」の情報に従う [必要があります](configure-multiple-emergency-numbers.md)。 

グローバルの場所のポリシーを編集して、マークされた新しい場所のポリシーを作成できます。場所のポリシーが関連付けられたサブネット内部に配置されていない場合や、場所のポリシーが直接割り当てられていない場合に、クライアントはグローバル ポリシーを取得します。マークされたポリシーは、サブネットまたはユーザーに割り当てられます。 

場所のポリシーを作成するには、作成するユーザーが RTCUniversalServerAdmins グループまたは CsVoiceAdministrator 管理者役割のメンバーか、あるいは同等の管理者権限とアクセス許可を持つ必要があります。

詳細については [、「Plan location policis for Skype for Business Server」を参照してください](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。 この手順のコマンドレットでは、次の値を使用して定義された場所ポリシーを使用します。 コマンドレットのパラメーターと値の詳細については [、「New-CsLocationPolicy」を参照してください](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)。


| **要素**                               | **値**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **True** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **免責事項** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | 会社のポリシーで場所の設定が要求されています。場所を設定しない場合、緊急サービスが緊急時に発見できません。場所を設定してください。  <br/> |
| UseLocationForE911Only  <br/>             | **False** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>場所のポリシーを作成するには

1. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。

    > [!NOTE]
    > **PstnUsage** の設定がグローバルの PstnUsages 一覧にあらかじめ存在していない場合、CsLocationPolicy は失敗します。

2. オプションで、次のコマンドレットを実行して、グローバルの場所のポリシーを編集します。

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. 次のコマンドレットを実行してマークされた場所のポリシーを作成します。

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. 次のコマンドレットを実行して、ステップ 3 で作成したマークされた場所のポリシーをユーザー ポリシーに適用します。

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```