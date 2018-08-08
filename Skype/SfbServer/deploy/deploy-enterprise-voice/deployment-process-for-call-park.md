---
title: ビジネス用の Skype のコール パークの展開プロセス
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: 展開プロセスとビジネス サーバーのエンタープライズ VoIP の Skype のコール パークの手順を実行します。
ms.openlocfilehash: 76046b8dbd39ecf9b17675ec8b3c1270a6c70122
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988312"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>ビジネス用の Skype のコール パークの展開プロセス
 
展開プロセスとビジネス サーバーのエンタープライズ VoIP の Skype のコール パークの手順を実行します。
  
コール パークには、保留中の 1 つの電話からの呼び出しを配置し、任意の電話から内部番号 (コール パーク軌道として呼ばれます) をダイヤルすることによって後で呼び出しを取得するのには、エンタープライズ VoIP ユーザーが有効にします。
  
コール パークを使用するコンポーネントが自動的にインストールし、エンタープライズ VoIP を展開するときにフロント エンド サーバーまたは Standard Edition サーバー上で有効になっています。 ただし、ユーザーが使用可能になる前に、コール パークを構成するのには次の手順を使用する必要があります。 
  
**コール パーク展開プロセス**

|**段階**|**手順**|**必要なグループおよび役割**|**「展開」のドキュメント**|
|:-----|:-----|:-----|:-----|
|オービット テーブルでコール パーク オービット範囲を構成する  <br/> |アプリケーションを使用して Skype ビジネス サーバーのコントロール パネルの**新規 CSCallParkOrbit**コマンドレットをコール パークの回り込みテーブルでの移動範囲を作成しに関連付けるアプリケーション サービスをホストしているパーク。 <br/> **注:** 既存のダイヤル プランとシームレスに統合、軌道の範囲は通常、仮想の拡張子のブロックとして構成します。 コール パーク オービット テーブルでオービット番号として Direct Inward Dialing (DID) 番号を指定することは、サポートされていません。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[作成またはビジネス用の Skype でコール パークの移動範囲を変更します。](create-or-modify-a-call-park-orbit-range.md) <br/> |
|コール パーク設定の構成  <br/> | **セット CsCpsConfiguration**コマンドレットを使用して、コール パーク設定を構成します。 最低限、停止の呼び出しがタイムアウトになったときに使用する代替の宛先を構成するのには [ **OnTimeoutURI** ] オプションを構成することをお勧めします。次の設定を構成することもできます。 <br/>  (省略可能)**EnableMusicOnHold**を有効にするか、保留中の音楽を無効にします。 <br/>  (省略可能)**MaxCallPickupAttempts**のフォールバック統一リソース識別子 (URI) への呼び出しを転送する前に応答側の電話に停止の呼び出しまでの呼び出し回数を決定します。 <br/>  (省略可能)**CallPickupTimeoutThreshold**の電話が鳴って電話呼び出しに応答した場所に戻る前に、駐機しているされた後に経過する時間の量を判断します。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[ビジネス用の Skype のコール パーク設定を構成します。](configure-call-park-settings.md) <br/> |
|必要に応じて、保留音をカスタマイズする  <br/> |カスタマイズし、オーディオ ファイルをアップロード、既定の音楽を使用したくない場合に、**セット CsCallParkServiceMusicOnHoldFile**コマンドレットを使用します。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[ビジネスのために保留中の inSkype コール パークの音楽をカスタマイズします。](customize-call-park-music-on-hold.md) <br/> |
|ユーザーに対してコール パークを有効にする音声ポリシーを構成します。  <br/> |ボイス ポリシーでユーザーのコール パークを有効にするのにビジネス サーバーのコントロール パネルまたは**EnableCallPark**オプションを使用して**セット CSVoicePolicy**コマンドレットの Skype を使用します。 <br/> 既定では、すべてのユーザーに対してコール パークが無効になります。  <br/> 複数の音声ポリシーが存在する場合、EnableCallPark プロパティが、既定のポリシーに対してだけでなく、それぞれの音声ポリシーに設定されているのを確認してください。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[ビジネス用の Skype のユーザーのコール パークを有効にします。](enable-call-park-for-users.md) <br/> |
|コール パーク正規化ルールの確認  <br/> |コール パーク オービットを正規化することはできません。正規化ルールにオービット範囲が含まれていないのを確認します。必要に応じて、オービットが正規化されるのを防ぐため、追加の正規化ルールを作成します。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[ビジネス用の Skype のコール パークの正規化ルールを確認します。](verify-normalization-rules-for-call-park.md) <br/> |
|コール パーク展開を確認します。  <br/> |通話の保留と取得をテストし、構成が予想どおりに動作することを確認します。  <br/> |-  <br/> |[(省略可能)ビジネス用の Skype のコール パーク展開を確認します。](optional-verify-call-park-deployment.md) <br/> |
   

