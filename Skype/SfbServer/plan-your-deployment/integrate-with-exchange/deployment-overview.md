---
title: オンプレミスユニファイド メッセージングと Skype for Business を統合する展開プロセスの概要
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1bcadf0a-ca3d-436f-a2a0-09329d487b18
description: '概要: Skype for Business Server を Exchange 2013 または 2016 に統合する計画を立てながら、このトピックを確認してください。'
ms.openlocfilehash: c6b2e70e9975182d9b6790b42a1120f66584bc7d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101563"
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>オンプレミスユニファイド メッセージングと Skype for Business を統合する展開プロセスの概要
 
**概要:** Skype for Business Server を Exchange 2013 または 2016 に統合する計画を立てながら、このトピックを確認してください。
  
 Exchange ユニファイド メッセージング (UM) を Skype for Business Server と統合する場合は、このトピックで説明するタスクを実行する必要があります。 また [、「Plan for Exchange Unified Messaging](unified-messaging.md)integration in Skype for Business」で説明されている計画と展開のベスト プラクティスを確認してください。 このトピックでは、「展開」のドキュメントの「Skype for Business Server の [エンタープライズ VoIP](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) の展開」の説明に従って、Skype for Business Server を展開し、Skype for Business Server のユーザーを有効にしているが、エンタープライズ VoIP を有効にするためのすべての展開および構成手順を実行していない可能性があります。
 
> [!NOTE]
> 以前に知られている Exchange ユニファイド メッセージングは、Skype for Business Server 2019 では使用できなくなりました。電話システムを使用してボイスメール メッセージを記録し、その記録をユーザーの Exchange メールボックスに残します。 詳細については [、「Plan Cloud ボイスメール サービス](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 」を参照してください。
 
## <a name="unified-messaging-integration-process"></a>ユニファイド メッセージング統合プロセス

> [!IMPORTANT]
> 組織の Exchange 管理者と調整して、円滑で成功した統合を実現するために、各ユーザーが実行するタスクを確認することが重要です。 
  
|**フェーズ**|**手順**|**必要なグループおよび役割**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|次のいずれかを展開します。  <br/> • メールボックス  <br/> Microsoft Exchange Server 2010 または最新のサービス パック  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |2013 Microsoft Exchange Serverを使用している場合は、Skype for Business Server と同じフォレストExchange Server別のフォレストに次の役割をインストールします。  <br/> • クライアント アクセス  <br/> • メールボックス  <br/> 2013 Microsoft Exchange Server Exchange ユニファイド メッセージング (UM) が異なるフォレストにインストールされている場合は、Skype for Business Server フォレストを信頼するために各 Exchange フォレストを構成します。  <br/> Exchange 2010 を使用している場合は、Skype for Business Server と同じフォレストExchange Server別のフォレストに次の役割をインストールします。  <br/> • ユニファイド メッセージング  <br/> • ハブ トランスポート  <br/> • クライアント アクセス  <br/> • メールボックス  <br/> Skype for Business Server と Exchange ユニファイド メッセージング (UM) が異なるフォレストにインストールされている場合は、Skype for Business Server フォレストを信頼するために各 Exchange フォレストを構成します。  <br/> |エンタープライズ管理者 (これが組織内で最初の Exchange Server である場合)  <br/> または  <br/> Exchange 組織管理者 (これが組織内で最初の Exchange Server ではない場合)  <br/> |お使いの Exchange Server のバージョンに適したドキュメントを参照してください。  <br/> Exchange Server 2010 または最新のサービス パック展開に関するドキュメント <br/> Exchange Server 2013 計画と展開 <br/> Exchange Server 2016 計画と展開|
|証明書をインストールします。  <br/> |信頼されたルート証明機関 (CA) から Exchange UM サーバーごとに証明書をダウンロードしてインストールします。 証明書は、Exchange UM と Skype for Business Server を実行しているサーバー間の相互トランスポート レベル セキュリティ (MTLS) に必要です。  <br/> |管理者  <br/> |[ユニファイド メッセージングを実行しているサーバー Exchange Server構成する](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|新しい Exchange UM SIP ダイヤル プランを作成して構成します。  <br/> |Exchange UM サーバーで、組織の特定の展開要件に基づいて SIP ダイヤル プランを作成します。  <br/> |Exchange 組織管理者  <br/> | [クライアントでのユニファイド メッセージングのMicrosoft Exchange Server](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|Exchange UM SIP ダイヤル プランのセキュリティ設定を構成します。  <br/> |トラフィックをエンタープライズ VoIPするには、Exchange UM SIP ダイヤル プランのセキュリティ設定を SIP セキュリティで保護またはセキュリティ **で保護されたとして****構成します**。 これは、環境に Lync Phone Edition デバイスを展開または展開する予定がある場合に特に重要な手順です。 Lync Phone Edition デバイスが Exchange UM 統合環境で機能するには、Skype for Business Server の暗号化設定が Exchange UM ダイヤル プランのセキュリティ設定と一致している必要があります。 詳細については、「展開」のドキュメントを参照してください。  <br/> |Exchange 組織管理者  <br/> |Exchange 2010 または最新 Service Pack の場合は、次のドキュメントも参照してください。  <br/> [UM ダイヤル プランで VoIP セキュリティを構成します](/previous-versions/office/exchange-server-2010/bb201721(v=exchg.141))。  <br/> Exchange 2013 については、「ユニファイド メッセージング [」を参照してください](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|Exchange UM SIP ダイヤル プランにユニファイド メッセージング サーバーを追加します。  <br/> |新しくインストールされたユニファイド メッセージング サーバーを、着信通話に応答および着信通話を処理できるようにするには、ユニファイド メッセージング サーバーを UM ダイヤル プランに追加しなければなりません。 この場合は、Exchange UM SIP ダイヤル プランにサーバーを追加します。  <br/> |管理者  <br/> Exchange Server 管理者  <br/> |Exchange 2010 または最新のサービス パックについては、「UM サーバーのプロパティを表示または構成 [する」を参照してください](/previous-versions/office/exchange-server-2010/aa998815(v=exchg.141))。  <br/> Exchange 2013 については、「ユニファイド メッセージング [」を参照してください](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|SIP アドレスでメールボックスを構成します。  <br/> |Exchange UM 機能を使用するユーザーのエンタープライズ VoIPに SIP アドレスを割り当てる。  <br/> |Skype for Business Server 管理者  <br/> Exchange 受信者管理者  <br/> |Exchange 2010 または最新のサービス パックについては、「ユーザーの SIP アドレスを変更する」 [をUM-Enabledしてください](/previous-versions/office/exchange-server-2010/dd335189(v=exchg.141))。  <br/> Exchange 2013 については、「ユニファイド メッセージング [」を参照してください](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|exchucutil.ps1 スクリプトを実行します。  <br/> |Exchange UM サービスを実行しているサーバーで、Exchange 管理シェルを開き、次の exchucutil.ps1スクリプトを実行します。 <br/> <br/> • Skype for Business Server に、Exchange UM Active Directory ドメイン サービス オブジェクト (特に、前のタスクで作成した SIP ダイヤル プラン) を読み取るアクセス許可を付与します。  <br/><br/> • Skype for Business Server Enterprise Edition プールまたは Standard Edition サーバーごとに、Active Directory にユニファイド メッセージング IP ゲートウェイ オブジェクトを作成し、このオブジェクトに対して有効になっているユーザーをホストエンタープライズ VoIP。  <br/><br/> • ゲートウェイごとに Exchange UM ハント グループを作成します。 ハント グループのパイロット ID は、対応するゲートウェイに関連付けられたダイヤル プランの名前になります。 複数のダイヤル プランが存在する場合は、これらは 1 対 1 でマップされる必要があります。  <br/> |Exchange 組織管理者  <br/> Exchange 受信者管理者  <br/> |[Microsoft Exchange でユニファイド メッセージングを構成するには、次のExchUCUtil.ps1](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|Skype for Business Server ダイヤル プランを構成します。  <br/> |Exchange 2010 と統合する場合は、Exchange UM ダイヤル プランの完全修飾ドメイン名 (FQDN) に一致する名前を持つ新しい エンタープライズ VoIP ダイヤル プランを作成します。  <br/> **注:** UM ダイヤル プランごとにこれを行う必要があります。 <br/> Exchange 2010 SP1 と統合する場合は、適切なグローバル/サイト レベルまたはプール レベルのダイヤル プランがエンタープライズ VoIP構成されていることを確認します。  <br/> **注:** Exchange 2010 SP1 と統合する場合、Skype for Business Server ダイヤル プランと Exchange UM SIP ダイヤル プラン名は一致する必要があります。 <br/> |RTCUniversalServerAdmins  <br/> |[Skype for Business Server でダイヤル プランを作成または変更する](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|Exchange UM 統合ツールを実行します。  <br/> | Skype for Business Server で、 **次のocsumutil.exe** 実行します。  <br/>  サブスクライバー アクセスおよび自動応答連絡先オブジェクトを作成します。 <br/>  Exchange UM ダイヤル プラン FQDN エンタープライズ VoIP一致する名前のダイヤル プランが作成済みである必要があります。 Exchange 2010 SP1 以降を実行している場合、ダイヤル プラン名は一致する必要がなく、この点に関するツールの警告は無視できます。 <br/>  このツールは、Active Directory for Exchange UM 設定をスキャンし、Skype for Business Server 管理者が連絡先オブジェクトを表示、作成、および編集できるようにすることで機能します。 <br/> |RTCUniversalServerAdmins  *および*  RTCUniversalUserAdmins <br/> **重要:** ユーザーを正常ocsumutil.exe実行するには、ユーザーがこれらの両方のグループに属している必要があります。 <br/> **注:** Contact オブジェクトを作成するには、新しい連絡先ocsumutil.exe格納されている Active Directory 組織単位 (OU) に対する正しいアクセス許可が必要です。 このアクセス許可は **、Grant-CsOUPermission コマンドレットを実行することで付与** できます。 詳細については、Skype for Business Server 管理シェルのドキュメントを参照してください。 <br/> |[Skype Exchange Serverユニファイド メッセージングの構成](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|必要に応じて、その他のエンタープライズ VoIP 構成ステップを実行します。  <br/> |サーバーまたはユーザーにエンタープライズ VoIP 設定をまだ構成していない場合、次の 1 つ以上の操作を実行します。  <br/> • 展開と構成  <br/> 公衆交換電話網 (PSTN) ゲートウェイと仲介サーバー  <br/> • 音声ポリシー、PSTN 使用法レコード、および発信通話ルートを定義します。  <br/> • ユーザーがユーザーのエンタープライズ VoIP。  <br/> • 必要に応じて、ダイヤル プランを使用して特定のユーザーを構成します。  <br/> 有効にするエンタープライズ VoIP 機能によっては、その他の構成ステップが必要となる場合があります。  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |次のセクションのトピックを参照してください。  <br/> • [Skype for Business で音声ポリシー、PSTN](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)使用法レコード、音声ルートを構成する <br/> • [Skype for business Server エンタープライズ VoIPに展開する](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|Exchange UM エンタープライズ VoIPユーザーを有効にする。  <br/> |Exchange UM サーバーで、ユニファイド メッセージング メールボックス ポリシーが作成され、各ユーザーが一意の内線番号の割り当てを持ち、ユーザーがユニファイド メッセージングを有効にするようにします。  <br/> |Exchange 受信者管理者  <br/> |Exchange 2010 または最新のサービス パックについては [、「Enable a User for Unified Messaging」を参照してください](/previous-versions/office/exchange-server-2010/bb124147(v=exchg.141))。  <br/> Exchange 2013 については、「ユニファイド メッセージング [」を参照してください](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
   




## <a name="see-also"></a>関連項目

[Skype for Business での Exchange ユニファイド メッセージング統合の計画](unified-messaging.md)