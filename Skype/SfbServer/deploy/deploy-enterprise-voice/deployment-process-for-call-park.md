---
title: Skype for Business のコール パークの展開プロセス
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
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Skype for Business Server エンタープライズ VoIP でのコール パークの展開プロセスとエンタープライズ VoIP。
ms.openlocfilehash: 0ddc46c391d362fde922e682db0813ad1c0d72bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812357"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Skype for Business のコール パークの展開プロセス
 
Skype for Business Server エンタープライズ VoIP でのコール パークの展開プロセスとエンタープライズ VoIP。
  
コール パークを使用すると、エンタープライズ VoIP ユーザーは 1 つの電話から通話を保留にした後、任意の電話から内部番号 (コール パーク オービットと呼ばれる) をダイヤルして通話を取得できます。
  
コール パークで使用するコンポーネントは、展開時にフロントエンド サーバーまたは Standard Edition サーバーに自動的にインストールされエンタープライズ VoIP。 ただし、ユーザーがコール パークを使用するには、次の手順を使用してコール パークを構成する必要があります。 
  
**コール パーク展開プロセス**

|**フェーズ**|**手順**|**必要なグループおよび役割**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|オービット テーブルでコール パーク オービット範囲を構成する  <br/> |Skype for Business Server コントロール パネルまたは **New-CSCallParkOrbit** コマンドレットを使用して、コール パーク オービット テーブルにオービット範囲を作成し、コール パーク アプリケーションをホストするアプリケーション サービスに関連付ける。 <br/> **注:** 既存のダイヤル プランとのシームレスな統合のために、オービット範囲は通常、仮想内線番号のブロックとして構成されます。 コール パーク オービット テーブルでオービット番号として Direct Inward Dialing (DID) 番号を指定することは、サポートされていません。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business でコール パーク オービット範囲を作成または変更する](create-or-modify-a-call-park-orbit-range.md) <br/> |
|コール パーク設定の構成  <br/> | **Set-CsCpsConfiguration** コマンドレットを使用してコール パーク設定を構成します。 少なくとも **、OnTimeoutURI** オプションを構成して、パークされた通話がタイム アウトするときに使用するフォールバック先を構成することをお勧めします。次の設定を構成することもできます。 <br/>  (オプション) **EnableMusicOnHold** を構成して保留音を有効または無効にします。 <br/>  (オプション) **MaxCallPickupAttempts** を構成して、パークされた通話が、代替 Uniform Resource Identifier (URI) に転送されるまでに、応答した電話にかけ直す回数を決定します。 <br/>  (オプション) **CallPickupTimeoutThreshold** を構成して、通話がパークされてから、呼び出しに応答した電話にかけ直されるまでの経過時間を決定します。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business でコール パーク設定を構成する](configure-call-park-settings.md) <br/> |
|必要に応じて、保留音をカスタマイズする  <br/> |既定の保留音を使用しない場合は、**Set-CsCallParkServiceMusicOnHoldFile** コマンドを使用して、音声ファイルをカスタマイズおよびアップロードします。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business でコール パーク保留音をカスタマイズする](customize-call-park-music-on-hold.md) <br/> |
|音声ポリシーを構成してユーザーのコール パークを有効にする  <br/> |音声ポリシーでユーザーのコール パークを有効にするには、Skype for Business Server コントロール パネルまたは **EnableCallPark** オプションを指定した **Set-CSVoicePolicy** コマンドレットを使用します。 <br/> 既定では、コール パークはすべてのユーザーに対して無効になっています。  <br/> 複数の音声ポリシーが存在する場合、EnableCallPark プロパティが、既定のポリシーに対してだけでなく、それぞれの音声ポリシーに設定されているのを確認してください。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business でユーザーのコール パークを有効にする](enable-call-park-for-users.md) <br/> |
|コール パーク正規化ルールの確認  <br/> |コール パーク オービットを正規化することはできません。 正規化ルールにオービット範囲が含まれていないのを確認します。 必要に応じて、オービットが正規化されるのを防ぐため、追加の正規化ルールを作成します。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business のコール パークの正規化ルールを確認する](verify-normalization-rules-for-call-park.md) <br/> |
|コール パークの展開を確認する  <br/> |通話の予約と取得をテストして、構成が期待した通り動作する必要があります。  <br/> |-  <br/> |[(省略可能)Skype for Business でのコール パーク展開の確認](optional-verify-call-park-deployment.md) <br/> |
   

