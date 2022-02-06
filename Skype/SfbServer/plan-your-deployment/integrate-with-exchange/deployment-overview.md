---
title: オンプレミスユニファイド メッセージングとユニファイド メッセージングを統合する展開プロセスSkype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1bcadf0a-ca3d-436f-a2a0-09329d487b18
description: '概要: 2013 または 2016 年にSkype for Business ServerをExchangeしながら、このトピックを確認してください。'
---

# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>オンプレミスユニファイド メッセージングとユニファイド メッセージングを統合する展開プロセスSkype for Business
 
**概要:** 2013 年または 2016 年Skype for Business ServerにExchangeこのトピックを確認してください。
  
 ユニファイド メッセージング (UM) と Exchange統合する場合は、このトピックでSkype for Business Serverタスクを実行する必要があります。 また、「プラン for Exchange ユニファイド メッセージング統合」で説明されている計画と展開のベスト プラクティスを[Skype for Business。](unified-messaging.md) このトピックでは、「展開」の説明に従って、Skype for Business Server を展開し、Skype for Business Server に対してユーザーを有効にしたが、エンタープライズ VoIP を有効にするためのすべての展開および構成手順を実行していない可能性があります。[エンタープライズ VoIPのSkype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)」を参照してください。
 
> [!NOTE]
> Exchange以前に知られているユニファイド メッセージングは Skype for Business Server 2019 では使用できなくなりました。電話システム を使用してボイスメール メッセージを記録し、その記録をユーザーの Exchange メールボックスに残します。 詳細については[、「プラン クラウド ボイスメール サービス](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)」を参照してください。
 
## <a name="unified-messaging-integration-process"></a>ユニファイド メッセージング統合プロセス

> [!IMPORTANT]
> 組織の管理者と調整して、Exchangeのタスクを確認して、円滑で成功した統合を実現することが重要です。 
  
|**フェーズ**|**手順**|**必要なグループおよび役割**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|次のいずれかを展開します。  <br/> • メールボックス  <br/> Microsoft Exchange Server 2010 または最新のサービス パック  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |2013 年 2013 年Microsoft Exchange Server使用している場合は、同じフォレストまたは別のフォレストExchange Serverの役割を次のようにインストールSkype for Business Server。  <br/> • クライアント アクセス  <br/> • メールボックス  <br/> 2013 Microsoft Exchange Serverおよび Exchange ユニファイド メッセージング (UM) が異なるフォレストにインストールされている場合は、各 Exchange フォレストを構成して、Skype for Business Server フォレストを信頼します。  <br/> 2010 年 2010 年Exchange使用している場合は、同じフォレストまたは別のフォレストにExchange Serverの役割をインストールSkype for Business Server。  <br/> • ユニファイド メッセージング  <br/> • ハブ トランスポート  <br/> • クライアント アクセス  <br/> • メールボックス  <br/> ユニファイド メッセージングSkype for Business ServerおよびExchangeユニファイド メッセージング (UM) が異なるフォレストにインストールされている場合は、各 Exchange フォレストを信頼Skype for Business Server構成します。  <br/> |エンタープライズ管理者 (これが組織内で最初の Exchange Server である場合)  <br/> または  <br/> Exchange 組織管理者 (これが組織内で最初の Exchange Server ではない場合)  <br/> |お使いの Exchange Server のバージョンに適したドキュメントを参照してください。  <br/> Exchange Server 2010 または最新のサービス パック展開に関するドキュメント <br/> Exchange Server 2013 計画と展開 <br/> Exchange Server 2016 計画と展開|
|証明書をインストールします。  <br/> |信頼できるルート証明機関 (CA) Exchange UM サーバーごとに証明書をダウンロードしてインストールします。 証明書は、UM とサーバーを実行しているサーバー間の相互トランスポート レベル セキュリティ (MTLS) にExchange必要Skype for Business Server。  <br/> |管理者  <br/> |[ユニファイド メッセージングを実行しているサーバー Exchange Server構成する](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|UM SIP ダイヤル プランの新Exchange作成および構成します。  <br/> |UM サーバー Exchange、組織の特定の展開要件に基づいて SIP ダイヤル プランを作成します。  <br/> |Exchange 組織管理者  <br/> | [クライアントでのユニファイド メッセージングのMicrosoft Exchange Server](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|UM SIP ダイヤル プランExchangeセキュリティ設定を構成します。  <br/> |トラフィックをエンタープライズ VoIPするには、UM SIP ダイヤル プランのセキュリティ設定を SIP セキュリティExchangeセキュリティで保護 **されたとして** 構成 **します**。 これは、環境に Lync 電話 エディション デバイスを展開または展開する予定がある場合に特に重要な手順です。 Lync 電話 Edition デバイスが Exchange UM 統合環境で機能するには、Skype for Business Server 暗号化設定が Exchange UM ダイヤル プランのセキュリティ設定と一致している必要があります。 詳細については、「展開」のドキュメントを参照してください。  <br/> |Exchange 組織管理者  <br/> |Exchange 2010 または最新 Service Pack の場合は、次のドキュメントも参照してください。  <br/> [UM ダイヤル プランで VoIP セキュリティを構成します](/previous-versions/office/exchange-server-2010/bb201721(v=exchg.141))。  <br/> 2013 Exchangeユニファイド メッセージング」[を参照してください](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|ユニファイド メッセージング サーバーを UM SIP ダイヤル プランExchangeに追加します。  <br/> |新しくインストールされたユニファイド メッセージング サーバーを、着信通話に応答および着信通話を処理できるようにするには、ユニファイド メッセージング サーバーを UM ダイヤル プランに追加しなければなりません。 この場合は、サーバーを UM SIP ダイヤル Exchangeに追加します。  <br/> |管理者  <br/> Exchange Server 管理者  <br/> |2010 Exchange最新のサービス パックについては、「UM サーバーのプロパティを表示または構成[する」を参照してください](/previous-versions/office/exchange-server-2010/aa998815(v=exchg.141))。  <br/> 2013 Exchangeユニファイド メッセージング」[を参照してください](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|SIP アドレスでメールボックスを構成します。  <br/> |UM 機能を使用するユーザーエンタープライズ VoIPのメールボックスに SIP アドレスExchange割り当てる。  <br/> |Skype for Business Server管理者  <br/> Exchange 受信者管理者  <br/> |2010 Exchange最新のサービス パックについては、「ユーザーの SIP アドレスを変更する[」をUM-Enabledしてください](/previous-versions/office/exchange-server-2010/dd335189(v=exchg.141))。  <br/> 2013 Exchangeユニファイド メッセージング」[を参照してください](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
|exchucutil.ps1 スクリプトを実行します。  <br/> |UM サービスを実行Exchangeサーバーで、Exchange 管理シェルを開き、exchucutil.ps1スクリプトを実行します。このスクリプトは次の手順を実行します。 <br/> <br/> • 前Skype for Business Server作成した SIP ダイヤル プランExchange UM Active Directory ドメイン サービス オブジェクトを読み取るアクセス許可を付与します。  <br/><br/> • Active Directory に、Skype for Business Server Enterprise Edition プールまたは Standard Edition サーバーごとにユニファイド メッセージング IP ゲートウェイ オブジェクトを作成し、このオブジェクトに対して有効になっているユーザーをホストエンタープライズ VoIP。  <br/><br/> • 各ゲートウェイExchange UM ハント グループを作成します。 ハント グループのパイロット ID は、対応するゲートウェイに関連付けられたダイヤル プランの名前になります。 複数のダイヤル プランが存在する場合は、これらは 1 対 1 でマップされる必要があります。  <br/> |Exchange 組織管理者  <br/> Exchange 受信者管理者  <br/> |[Microsoft Exchangeでユニファイド メッセージングを構成ExchUCUtil.ps1](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|ダイヤル プランSkype for Business Server構成します。  <br/> |Exchange 2010 と統合する場合は、Exchange UM ダイヤル プラン完全修飾ドメイン名 (FQDN) に一致する名前を持つ新しい エンタープライズ VoIP ダイヤル プランを作成します。  <br/> **注:** UM ダイヤル プランごとにこれを行う必要があります。 <br/> 2010 SP1 Exchange統合する場合は、適切なグローバル/サイト レベルまたはプール レベルのダイヤル プランがエンタープライズ VoIPされていることを確認します。  <br/> **注:** Exchange 2010 SP1 と統合する場合、Skype for Business Server ダイヤル プランと Exchange UM SIP ダイヤル プラン名は一致する必要があります。 <br/> |RTCUniversalServerAdmins  <br/> |[ダイヤル プランを作成または変更するには、Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|UM 統合ツールExchange実行します。  <br/> | 次の **Skype for Business Server、次** ocsumutil.exe実行します。  <br/>  サブスクライバー アクセスおよび自動応答連絡先オブジェクトを作成します。 <br/>  UM ダイヤル プラン FQDN エンタープライズ VoIP一致する名前のダイヤル プランExchange検証します。 2010 SP1 Exchange以降を実行している場合、ダイヤル プラン名は一致する必要がなく、この点に関するツールの警告は無視できます。 <br/>  このツールは、Active Directory で UM Exchangeをスキャンし、Skype for Business Server管理者が連絡先オブジェクトを表示、作成、および編集できるようにすることで機能します。 <br/> |RTCUniversalServerAdmins  *および*  RTCUniversalUserAdmins <br/> **大事な：** ユーザーを正常ocsumutil.exe実行するには、ユーザーがこれらの両方のグループに属している必要があります。 <br/> **注:** Contact オブジェクトを作成するには、新しい連絡先ocsumutil.exe格納されている Active Directory 組織単位 (OU) に対する正しいアクセス許可が必要です。 このアクセス許可は、 **Grant-CsOUPermission コマンドレットを実行することで付与** できます。 詳細については、「管理シェルのSkype for Business Server」を参照してください。 <br/> |[ボイス メールExchange Serverユニファイド メッセージングSkype for Business Server構成する](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|必要に応じて、その他のエンタープライズ VoIP 構成ステップを実行します。  <br/> |サーバーまたはユーザーにエンタープライズ VoIP 設定をまだ構成していない場合、次の 1 つ以上の操作を実行します。  <br/> • 展開と構成  <br/> 公衆交換電話網 (PSTN) ゲートウェイと仲介サーバー  <br/> • 音声ポリシー、PSTN 使用法レコード、および発信通話ルートを定義します。  <br/> • ユーザーがユーザーのエンタープライズ VoIP。  <br/> • 必要に応じて、ダイヤル プランを使用して特定のユーザーを構成します。  <br/> 有効にするエンタープライズ VoIP 機能によっては、その他の構成ステップが必要となる場合があります。  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |次のセクションのトピックを参照してください。  <br/> • [音声ポリシー、PSTN 使用法レコード、](../../deploy/deploy-enterprise-voice/voice-and-pstn.md)および音声ルートを構成Skype for Business <br/> • [エンタープライズ VoIPにSkype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|ユーザーエンタープライズ VoIP UM を有効Exchangeします。  <br/> |Exchange UM サーバーで、ユニファイド メッセージング メールボックス ポリシーが作成され、各ユーザーが一意の内線番号の割り当てを持ち、ユーザーがユニファイド メッセージングを有効にするようにします。  <br/> |Exchange 受信者管理者  <br/> |2010 Exchange最新のサービス パックについては、「Enable [a User for Unified Messaging」を参照してください](/previous-versions/office/exchange-server-2010/bb124147(v=exchg.141))。  <br/> 2013 Exchangeユニファイド メッセージング」[を参照してください](/exchange/unified-messaging-exchange-2013-help)。  <br/> |
   




## <a name="see-also"></a>関連項目

[ユニファイド メッセージングExchange統合を計画Skype for Business](unified-messaging.md)