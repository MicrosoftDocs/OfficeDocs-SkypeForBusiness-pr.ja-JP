---
title: Skype for Business でのグループ通話ピックアップの展開プロセス
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
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Skype for Business Server のグループ通話ピックアップの展開プロセスとエンタープライズ VoIP。
ms.openlocfilehash: 5c89522828e5e5a0dc04ffccb0907c0a2cb8a008
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812347"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Skype for Business でのグループ通話ピックアップの展開プロセス
 
Skype for Business Server のグループ通話ピックアップの展開プロセスとエンタープライズ VoIP。
  
グループ通話ピックアップを使用すると、ユーザーは自分の電話から同僚への着信呼び出しに応答できます。 
  
 グループ通話ピックアップが使用するコンポーネントは、展開時にフロントエンド サーバーまたは Standard Edition サーバーに自動的にインストールされエンタープライズ VoIP。 ただし、ユーザーがグループ通話ピックアップを使用するには、次の手順を使用してグループ通話ピックアップを構成する必要があります。
  
**グループ通話ピックアップの展開プロセス**

|**フェーズ**|**手順**|**必要なグループおよび役割**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|トポロジで SEFAUtil ツールを有効にする|新しい信頼New-CsTrustedApplicationPoolプールを作成するには、次のコマンドレットを使用します。 SEFAUtil New-CsTrustedApplication信頼されたアプリケーションとして指定するには、次のコマンドレットを使用します。 トポロジをEnable-CsTopologyコマンドレットを実行します。 まだインストールしていない場合は、この場所から Skype for Business Server バージョンの SEFAUtil ツールをダウンロードし、手順 1 で作成した信頼されたアプリケーション プールにインストールします。 SEFAUtil が正しく実行されていることを確認するには、SEFAUtil を実行して、展開内のユーザーの呼び出し転送設定を表示します。 |RTCUniversalServerAdmins  <br/> |[Skype for Business で SEFAUtil ツールを展開する](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Skype for Business Server 2015 リソース キット ツールのドキュメント](../../management-tools/resource-kit-tools.md)。 (Skype for Business Server の場合は、現在のバージョンのツールを使用する必要がありますが、Lync Server 2013 のこのドキュメントは引き続き適用されます)。  <br/> |
|コール パーク オービット テーブルで通話ピックアップ番号の範囲を構成する  <br/> |**New-CSCallParkOrbit** コマンドレットを使用して、コール パーク オービット テーブルに通話ピックアップ番号の範囲を作成し、通話ピックアップ範囲に **GroupPickup** 型を割り当てる。  <br/> 既存のダイヤル プランとシームレスに統合するには、通常、番号範囲は仮想内線番号のブロックとして構成されます。 コール パーク オービット テーブルの範囲番号としての Direct Inward Dialing (DID) 番号の割り当てはサポートされていません。  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Skype for Business でグループ通話ピックアップ番号の範囲を作成または変更する](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|ユーザーに通話ピックアップ番号を割り当て、ユーザーのグループ通話ピックアップを有効にする  <br/> |SEFAUtil リソース キット ツールの /enablegrouppickup パラメーターを使用して、グループ通話ピックアップを有効にし、ユーザーに通話ピックアップ番号を割り当てる。  <br/> |-  <br/> |[ユーザーのグループ通話ピックアップを有効にし、Skype for Business でグループ番号を割り当てる](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|割り当てられた通話ピックアップ番号とその他の関心のある番号をユーザーに通知する  <br/> |ユーザーのグループ通話ピックアップを有効にした後、電子メールなどのメカニズムを使用して、ユーザーに通話ピックアップ グループ番号を通知します。 監視する可能性があるグループの通話ピックアップ グループ番号をユーザーに通知します。 ユーザーは、同じグループにいなくても他のユーザーの通話を取得できるので、複数のグループの通話ピックアップ グループ番号が必要になる場合があります。  <br/> |-  <br/> ||
|グループ通話ピックアップの展開を確認する  <br/> | 呼び出しの配置と取得をテストして、構成が期待通り動作する必要があります。 少なくとも、以下を確認してください。 <br/>  グループ通話ピックアップが有効になっているユーザーを呼び出し、別のユーザーに通話を取得します。 もう一方のユーザーは、同じグループに含め、別のグループに含め、またはグループ通話ピックアップを有効にすることはできません。 <br/>  グループ通話ピックアップが有効になっているユーザーに電話をかけ、通話に応答しない。 <br/> |-  <br/> ||
   

