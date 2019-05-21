---
title: Skype for Business のコールパークの展開プロセス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: Skype for Business Server Enterprise Voice のコールパークの展開プロセスと手順。
ms.openlocfilehash: 972a8cec2794afeebc0f5ab65d89291e78b7211e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289014"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>Skype for Business のコールパークの展開プロセス
 
Skype for Business Server Enterprise Voice のコールパークの展開プロセスと手順。
  
コールパークエンタープライズボイスユーザーは、1つの電話から通話を保留にすることができます。通話を発信するには、任意の電話から内部番号 (通話パーク軌道と呼びます) をダイヤルする必要があります。
  
エンタープライズボイスの展開時に、コールパークで使用されるコンポーネントは、フロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされ、有効になります。 ただし、ユーザーが使用できるようになる前に、次の手順を使用してコールパークを設定する必要があります。 
  
**コール パーク展開プロセス**

|**段階**|**手順**|**必要なグループおよび役割**|**「展開」のドキュメント**|
|:-----|:-----|:-----|:-----|
|オービット テーブルでコール パーク オービット範囲を構成する  <br/> |Skype for Business Server コントロールパネルまたは**CSCallParkOrbit**コマンドレットを使用して、呼び出しパークのテーブルに軌道範囲を作成し、それを call パークアプリケーションをホストするアプリケーションサービスに関連付けます。 <br/> **注:** 既存のダイヤルプランとのシームレスな統合の場合、オービット範囲は通常、仮想拡張機能のブロックとして構成されます。 コール パーク オービット テーブルでオービット番号として Direct Inward Dialing (DID) 番号を指定することは、サポートされていません。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business のコールパーク範囲を作成または変更する](create-or-modify-a-call-park-orbit-range.md) <br/> |
|コール パーク設定の構成  <br/> | **CsCpsConfiguration**コマンドレットを使用して、コールパーク設定を構成します。 少なくとも、[ **Ontimeouturi** ] オプションを構成して、保留中の通話がタイムアウトしたときに使うフォールバック先を構成することをお勧めします。次の設定を構成することもできます。 <br/>  (オプション) **EnableMusicOnHold** を構成して保留音を有効または無効にします。 <br/>  (オプション) **MaxCallPickupAttempts** を構成して、パークされた通話が、代替 Uniform Resource Identifier (URI) に転送されるまでに、応答した電話にかけ直す回数を決定します。 <br/>  (オプション) **CallPickupTimeoutThreshold** を構成して、通話がパークされてから、呼び出しに応答した電話にかけ直されるまでの経過時間を決定します。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business のコールパーク設定を構成する](configure-call-park-settings.md) <br/> |
|必要に応じて、保留音をカスタマイズする  <br/> |既定の保留音を使用しない場合は、**Set-CsCallParkServiceMusicOnHoldFile** コマンドを使用して、音声ファイルをカスタマイズおよびアップロードします。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[通話パークを保留にする Skype for Business での音声通話](customize-call-park-music-on-hold.md) <br/> |
|音声ポリシーを構成してユーザーのコールパークを有効にする  <br/> |Skype for Business Server コントロールパネルまたは**CSVoicePolicy**コマンドレットを使用して、[ **Enablecallpark** ] オプションを使用して、ボイスポリシーのユーザーに対してコールパークを有効にします。 <br/> 既定では、すべてのユーザーに対して [コールパーク] が無効になっています。  <br/> 複数の音声ポリシーが存在する場合、EnableCallPark プロパティが、既定のポリシーに対してだけでなく、それぞれの音声ポリシーに設定されているのを確認してください。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business のユーザーに対してコールパークを有効にする](enable-call-park-for-users.md) <br/> |
|コール パーク正規化ルールの確認  <br/> |コール パーク オービットを正規化することはできません。正規化ルールにオービット範囲が含まれていないのを確認します。必要に応じて、オービットが正規化されるのを防ぐため、追加の正規化ルールを作成します。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business のコールパークの正規化ルールを確認する](verify-normalization-rules-for-call-park.md) <br/> |
|コールパークの展開を確認する  <br/> |通話の保留と取得をテストし、構成が予想どおりに動作することを確認します。  <br/> |-  <br/> |[省略Skype for Business のコールパークの展開を確認する](optional-verify-call-park-deployment.md) <br/> |
   

