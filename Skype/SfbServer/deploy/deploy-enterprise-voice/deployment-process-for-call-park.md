---
title: コール パークの展開プロセス (Skype for Business
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
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: 展開プロセスと、コール パークの手順をSkype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: b734aba8c2944cab37071773d27bbc9411a18b9c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861854"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>コール パークの展開プロセス (Skype for Business
 
展開プロセスと、コール パークの手順をSkype for Business Server エンタープライズ VoIP。
  
コール パークを使用すると、エンタープライズ VoIP ユーザーは 1 つの電話から通話を保留にしてから、任意の電話から内部番号 (コール パーク オービットと呼ばれる) をダイヤルして後で通話を取得できます。
  
コール パークが使用するコンポーネントは、展開時にフロント エンド サーバーまたは Standard Edition サーバーに自動的にインストールされエンタープライズ VoIP。 ただし、ユーザーが利用できる前に、次の手順を使用してコール パークを構成する必要があります。 
  
**コール パーク展開プロセス**

|**フェーズ**|**手順**|**必要なグループおよび役割**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|オービット テーブルでコール パーク オービット範囲を構成する  <br/> |Skype for Business Server コントロール パネルまたは **New-CSCallParkOrbit** コマンドレットを使用して、呼び出しパーク オービット テーブルにオービット範囲を作成し、それらを呼び出しパーク アプリケーションをホストする Application サービスに関連付ける。 <br/> **注:** 既存のダイヤル プランとのシームレスな統合のために、オービット範囲は通常、仮想内線番号のブロックとして構成されます。 コール パーク オービット テーブルでオービット番号として Direct Inward Dialing (DID) 番号を指定することは、サポートされていません。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[コール パーク オービット範囲を作成または変更Skype for Business](create-or-modify-a-call-park-orbit-range.md) <br/> |
|コール パーク設定の構成  <br/> | **Set-CsCpsConfiguration** コマンドレットを使用して、コール パークの設定を構成します。 少なくとも、パークされた通話がアウトした場合に使用するフォールバック先を構成する **OnTimeoutURI** オプションを構成することをお勧めします。また、次の設定を構成することもできます。 <br/>  (オプション) **EnableMusicOnHold** を構成して保留音を有効または無効にします。 <br/>  (オプション) **MaxCallPickupAttempts** を構成して、パークされた通話が、代替 Uniform Resource Identifier (URI) に転送されるまでに、応答した電話にかけ直す回数を決定します。 <br/>  (オプション) **CallPickupTimeoutThreshold** を構成して、通話がパークされてから、呼び出しに応答した電話にかけ直されるまでの経過時間を決定します。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[[通話パークの設定] を [Skype for Business](configure-call-park-settings.md) <br/> |
|必要に応じて、保留音をカスタマイズする  <br/> |既定の保留音を使用しない場合は、**Set-CsCallParkServiceMusicOnHoldFile** コマンドを使用して、音声ファイルをカスタマイズおよびアップロードします。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Businessで通話パークの音楽を保留にカスタマイズする](customize-call-park-music-on-hold.md) <br/> |
|ユーザーの通話パークを有効にする音声ポリシーを構成する  <br/> |音声Skype for Business Serverユーザーのコール パークを有効にするには **、EnableCallPark** オプションを使用して、コントロール パネルまたは **Set-CSVoicePolicy** コマンドレットを使用します。 <br/> 既定では、通話パークは、すべてのユーザーに対して無効になっています。  <br/> 複数の音声ポリシーが存在する場合、EnableCallPark プロパティが、既定のポリシーに対してだけでなく、それぞれの音声ポリシーに設定されているのを確認してください。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[[ユーザーの通話パークを有効にする] Skype for Business](enable-call-park-for-users.md) <br/> |
|コール パーク正規化ルールの確認  <br/> |コール パーク オービットを正規化することはできません。 正規化ルールにオービット範囲が含まれていないのを確認します。 必要に応じて、オービットが正規化されるのを防ぐため、追加の正規化ルールを作成します。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[コール パークの正規化ルールをSkype for Business](verify-normalization-rules-for-call-park.md) <br/> |
|コール パークの展開を確認する  <br/> |駐車場をテストし、呼び出しを取得して、構成が期待した通り動作します。  <br/> |-  <br/> |[(省略可能)[通話パークの展開を確認する] Skype for Business](optional-verify-call-park-deployment.md) <br/> |
   

