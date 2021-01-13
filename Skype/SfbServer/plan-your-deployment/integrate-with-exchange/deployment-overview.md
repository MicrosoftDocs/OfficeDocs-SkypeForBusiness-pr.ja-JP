---
title: オンプレミスのユニファイド メッセージングと Skype for Business を統合する展開プロセスの概要
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
description: '概要: Skype for Business Server と Exchange 2013 または 2016 の統合を計画する場合は、このトピックを確認してください。'
ms.openlocfilehash: 8171d8f7191b4b0db6fbb3deee76ab411b2ce25b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810127"
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>オンプレミスのユニファイド メッセージングと Skype for Business を統合する展開プロセスの概要
 
**概要:** Skype for Business Server と Exchange 2013 または 2016 の統合を計画する場合は、このトピックを確認してください。
  
 Exchange ユニファイド メッセージング (UM) を Skype for Business Server と統合する場合は、このトピックで説明するタスクを実行する必要があります。 また [、「Plan for Exchange Unified Messaging integration in Skype for Business」](unified-messaging.md)で説明されている計画と展開のベスト プラクティスを必ず確認してください。 このトピックでは、Skype for Business Server と、仲介サーバーを一緒に展開し、Skype for Business Server に対してユーザーを有効にしているが、「展開」のドキュメントの「Skype for [Business](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) Server の エンタープライズ VoIP の展開」で説明するように、すべての展開および構成手順を実行して エンタープライズ VoIP を有効にしていない可能性を前提にしています。
 
> [!NOTE]
> 以前に知られている Exchange ユニファイド メッセージングは、Skype for Business Server 2019 では使用できなくなりました。Skype for Business Server 2019 では、電話システムを使用してボイスメール メッセージを録音し、その録音をユーザーの Exchange メールボックスに残します。 詳細 [については、「クラウド ボイスメール サービスを計画](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) する」を参照してください。
 
## <a name="unified-messaging-integration-process"></a>ユニファイド メッセージング統合プロセス

> [!IMPORTANT]
> スムーズで正常な統合を実現するために、組織の Exchange 管理者と調整して、各ユーザーが実行するタスクを確認することが重要です。 
  
|**フェーズ**|**手順**|**必要なグループおよび役割**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|次のいずれかを展開します。  <br/> • メールボックス  <br/> Microsoft Exchange Server 2010 または最新の Service Pack  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |Microsoft Exchange Server 2013 を使用している場合は、次の Exchange Server の役割を Skype for Business Server と同じフォレストまたは別のフォレストにインストールします。  <br/> • クライアント アクセス  <br/> • メールボックス  <br/> 2013 Microsoft Exchange Server Exchange ユニファイド メッセージング (UM) が異なるフォレストにインストールされている場合は、Skype for Business Server フォレストを信頼する各 Exchange フォレストを構成します。  <br/> Exchange 2010 を使用している場合は、次の Exchange Server の役割を Skype for Business Server と同じフォレストまたは別のフォレストにインストールします。  <br/> • ユニファイド メッセージング  <br/> • ハブ トランスポート  <br/> • クライアント アクセス  <br/> • メールボックス  <br/> Skype for Business Server と Exchange ユニファイド メッセージング (UM) が異なるフォレストにインストールされている場合は、各 Exchange フォレストを構成して Skype for Business Server フォレストを信頼します。  <br/> |エンタープライズ管理者 (これが組織内で最初の Exchange Server である場合)  <br/> または  <br/> Exchange 組織管理者 (これが組織内で最初の Exchange Server ではない場合)  <br/> |お使いの Exchange Server のバージョンに適したドキュメントを参照してください。  <br/> Exchange Server 2010 または最新の Service Pack 展開に関するドキュメント <br/> Exchange Server 2013 の計画と展開 <br/> Exchange Server 2016 の計画と展開|
|証明書をインストールします。  <br/> |信頼されたルート証明機関 (CA) から各 Exchange UM サーバーの証明書をダウンロードしてインストールします。 証明書は、Exchange UM を実行しているサーバーと Skype for Business Server の間の相互トランスポート レベル セキュリティ (MTLS) に必要です。  <br/> |管理者  <br/> |[ユニファイド メッセージングを実行しているサーバーでExchange Serverを構成する](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|新しい Exchange UM SIP ダイヤル プランを作成して構成します。  <br/> |Exchange UM サーバーで、組織の特定の展開要件に基づいて SIP ダイヤル プランを作成します。  <br/> |Exchange 組織管理者  <br/> | [Microsoft Exchange Server でのユニファイド メッセージングのMicrosoft Exchange Server](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|Exchange UM SIP ダイヤル プランのセキュリティ設定を構成します。  <br/> |トラフィックをエンタープライズ VoIPするには、Exchange UM SIP ダイヤル プランのセキュリティ設定を [セキュリティで保護された **SIP]** または [セキュリティで保護] として **構成します**。 これは、環境に Lync Phone Edition デバイスを展開または展開する予定がある場合に特に重要な手順です。 Lync Phone Edition デバイスが Exchange UM 統合環境で機能するには、Skype for Business Server の暗号化設定が Exchange UM ダイヤル プランのセキュリティ設定と一致している必要があります。 詳細については、「展開」のドキュメントを参照してください。  <br/> |Exchange 組織管理者  <br/> |Exchange 2010 または最新 Service Pack の場合は、次のドキュメントも参照してください。  <br/> [UM ダイヤル プランで VoIP セキュリティを構成します](https://go.microsoft.com/fwlink/p/?LinkId=268697)。  <br/> Exchange 2013 については、「ユニファイド メッセージング」 [を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|ユニファイド メッセージング サーバーを Exchange UM SIP ダイヤル プランに追加します。  <br/> |新しくインストールされたユニファイド メッセージング サーバーを、着信通話に応答および着信通話を処理できるようにするには、ユニファイド メッセージング サーバーを UM ダイヤル プランに追加しなければなりません。 この場合は、サーバーを Exchange UM SIP ダイヤル プランに追加します。  <br/> |管理者  <br/> Exchange Server 管理者  <br/> |Exchange 2010 または最新のサービス パックについては、「UM サーバーのプロパティを表示または構成 [する」を参照してください](https://go.microsoft.com/fwlink/p/?linkId=268682)。  <br/> Exchange 2013 については、「ユニファイド メッセージング」 [を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|SIP アドレスでメールボックスを構成します。  <br/> |EXCHANGE UM 機能を使用するユーザーのメールボックスエンタープライズ VoIPに SIP アドレスを割り当てる。  <br/> |Skype for Business Server 管理者  <br/> Exchange 受信者管理者  <br/> |Exchange 2010 または最新のサービス パックについては、「ユーザーの SIP アドレスを変更する」をUM-Enabled [してください](https://go.microsoft.com/fwlink/p/?LinkId=268699)。  <br/> Exchange 2013 については、「ユニファイド メッセージング」 [を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
|exchucutil.ps1 スクリプトを実行します。  <br/> |Exchange UM サービスを実行しているサーバーで、Exchange 管理シェル を開き、次のexchucutil.ps1スクリプトを実行します。 <br/> <br/> • Exchange UM Active Directory ドメイン サービス オブジェクト(具体的には、前のタスクで作成された SIP ダイヤル プラン) を読み取るアクセス許可を Skype for Business Server に付与します。  <br/><br/> • 各 Skype for Business Server Enterprise Edition プールまたは エンタープライズ VoIP に対して有効になっているユーザーをホストする Standard Edition サーバーの、Active Directory にユニファイド メッセージング IP ゲートウェイ オブジェクトを作成します。  <br/><br/> • ゲートウェイごとに Exchange UM ハント グループを作成します。 ハント グループのパイロット ID は、対応するゲートウェイに関連付けられたダイヤル プランの名前になります。 複数のダイヤル プランが存在する場合は、これらは 1 対 1 でマップされる必要があります。  <br/> |Exchange 組織管理者  <br/> Exchange 受信者管理者  <br/> |[ユニファイド メッセージングを使用して Microsoft Exchange でユニファイド メッセージングをExchUCUtil.ps1](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|Skype for Business Server ダイヤル プランを構成します。  <br/> |Exchange 2010 と統合する場合は、Exchange UM ダイヤル プランの完全修飾ドメイン名 (FQDN) と一致する名前を持つ新しい エンタープライズ VoIP ダイヤル プランを作成します。  <br/> **注:** UM ダイヤル プランごとにこれを行う必要があります。 <br/> Exchange 2010 SP1 と統合する場合は、適切なグローバル/サイト レベルまたはプール レベルのダイヤル エンタープライズ VoIP構成されていることを確認します。  <br/> **注:** Exchange 2010 SP1 と統合している場合は、Skype for Business Server ダイヤル プランと Exchange UM SIP ダイヤル プラン名を一致する必要があります。 <br/> |RTCUniversalServerAdmins  <br/> |[Skype for Business Server でダイヤル プランを作成または変更する](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|Exchange UM 統合ツールを実行します。  <br/> | Skype for Business Server で、次のコマンド **ocsumutil.exe** 実行します。  <br/>  サブスクライバー アクセスおよび自動応答連絡先オブジェクトを作成します。 <br/>  Exchange UM ダイヤル プランの FQDN エンタープライズ VoIP一致する名前のダイヤル プランが 1 つ作成済みか確認します。 Exchange 2010 SP1 以降を実行している場合、ダイヤル プラン名は一致する必要はなく、この点に関するツールの警告は無視できます。 <br/>  このツールは、Exchange UM 設定の Active Directory をスキャンし、Skype for Business Server 管理者が連絡先オブジェクトを表示、作成、および編集できるようにすることで機能します。 <br/> |RTCUniversalServerAdmins  *および*  RTCUniversalUserAdmins <br/> **重要:** ユーザーがocsumutil.exeするには、ユーザーがこれらの両方のグループに属している必要があります。 <br/> **注:** 連絡先オブジェクトを作成するには、連絡先オブジェクトを実行するocsumutil.exe、新しい連絡先オブジェクトが格納されている Active Directory 組織単位 (OU) に対する適切なアクセス許可を持っている必要があります。 このアクセス許可は **、Grant-CsOUPermission コマンドレットを実行することで付与** できます。 詳細については、Skype for Business Server 管理シェルのドキュメントを参照してください。 <br/> |[Skype for Business Server Exchange Serverユニファイド メッセージングの構成](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|必要に応じて、その他のエンタープライズ VoIP 構成ステップを実行します。  <br/> |サーバーまたはユーザーにエンタープライズ VoIP 設定をまだ構成していない場合、次の 1 つ以上の操作を実行します。  <br/> • 展開と構成  <br/> 公衆交換電話網 (PSTN) ゲートウェイと仲介サーバー  <br/> • 音声ポリシー、PSTN 使用法レコード、および発信通話ルートを定義します。  <br/> • ユーザーに対してエンタープライズ VoIP。  <br/> • 必要に応じて、ダイヤル プランを使用して特定のユーザーを構成します。  <br/> 有効にするエンタープライズ VoIP 機能によっては、その他の構成ステップが必要となる場合があります。  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |次のセクションのトピックを参照してください。  <br/> • [Skype for Business で音声ポリシー、PSTN 使用法レコード、およびボイス ルートを構成する](../../deploy/deploy-enterprise-voice/voice-and-pstn.md) <br/> • [Skype for Business Server エンタープライズ VoIP展開する](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|Exchange UM エンタープライズ VoIPを有効にする。  <br/> |Exchange UM サーバーで、ユニファイド メッセージング メールボックス ポリシーが作成され、各ユーザーが一意の内線番号の割り当てを持っている必要があります。その後、ユーザーに対してユニファイド メッセージングを有効にします。  <br/> |Exchange 受信者管理者  <br/> |Exchange 2010 または最新のサービス パックについては、「ユニファイド メッセージングのユーザーを有効にする」 [を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=268701)。  <br/> Exchange 2013 については、「ユニファイド メッセージング」 [を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=266579)。  <br/> |
   




## <a name="see-also"></a>関連項目

[Skype for Business での Exchange ユニファイド メッセージングの統合を計画する](unified-messaging.md)
