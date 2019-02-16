---
title: オンプレミス ユニファイド メッセージングと Skype for Business を統合するための展開プロセスの概要
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1bcadf0a-ca3d-436f-a2a0-09329d487b18
description: '概要: ビジネスのサーバーで Exchange 2013 または 2016 の Skype を統合するために計画するときにこのトピックを参照します。'
ms.openlocfilehash: a0ab1ac2fc1805445f54772ea64556c3a3e80d57
ms.sourcegitcommit: 6d4b99de7233e91dbab4f08331dac4d88c51d9e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "30059174"
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>オンプレミス ユニファイド メッセージングと Skype for Business を統合するための展開プロセスの概要
 
**の概要:** ビジネスのサーバーで Exchange 2013 または 2016 の Skype を統合するために計画するときに、このトピックを確認します。
  
 Skype ビジネス サーバーの Exchange ユニファイド メッセージング (UM) と統合する場合は、このトピックで説明されているタスクを行う必要があります。 [ビジネス用の Skype での Exchange ユニファイド メッセージング統合の計画](unified-messaging.md)」に記載の計画と展開ベスト プラクティスを確認することを確認してあります。 ここでは配置されている仲介サーバーを持つサーバーをビジネスの Skype を展開し、ビジネス サーバー、Skype のユーザーを有効にしているが、実行したことがありませんがエンタープライズ VoIP を有効に、すべての展開と構成の手順展開に関するドキュメントでは、 [Skype のビジネス サーバーでエンタープライズ VoIP の展開](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)で説明します。
 
> [!NOTE]
> ユニファイド メッセージングと呼ばれていたになって Skype ビジネス サーバー 2019 は、電話システムを使用して、ボイスメールのメッセージを記録し、ユーザーの Exchange メールボックスに記録を残すのために使用できます。 詳細については、[クラウドのボイスメールの計画サービス](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)を参照してください。
 
## <a name="unified-messaging-integration-process"></a>ユニファイド メッセージング統合プロセス

> [!IMPORTANT]
> 重要なことがスムーズに成功した統合を確実に実行が協力して、組織の Exchange 管理者は、タスクを確認するとするのです。 
  
|**フェーズ**|**ステップ**|**必要なグループおよび役割**|**「展開」のドキュメント**|
|:-----|:-----|:-----|:-----|
|次のいずれかを展開します。  <br/> • メールボックス  <br/> Microsoft Exchange Server 2010 または最新の service pack  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |Microsoft Exchange Server 2013 を使用する場合、ビジネス サーバーを同じフォレストまたは別のフォレストのいずれかの Skype としての次の Exchange Server の役割をインストールします。  <br/> • クライアント アクセス  <br/> • メールボックス  <br/> 2013 の Microsoft Exchange Server および Exchange ユニファイド メッセージング (UM) が別のフォレスト内にインストールされている場合は、Business Server フォレストの Skype を信頼する場合は、各 Exchange フォレストを構成します。  <br/> Exchange 2010 を使用する場合、ビジネス サーバーを同じフォレストまたは別のフォレストのいずれかの Skype としての次の Exchange Server の役割をインストールします。  <br/> • はユニファイド メッセージング  <br/> • ハブ トランスポート  <br/> • クライアント アクセス  <br/> • メールボックス  <br/> Skype ビジネス サーバーおよび Exchange ユニファイド メッセージング (UM) は別々 のフォレストにインストールする場合は、Business Server フォレストの Skype を信頼する場合は、各 Exchange フォレストを構成します。  <br/> |エンタープライズ管理者 (これが組織内で最初の Exchange Server である場合)  <br/> - または -  <br/> Exchange 組織管理者 (これが組織内で最初の Exchange Server ではない場合)  <br/> |お使いの Exchange Server のバージョンに適したドキュメントを参照してください。  <br/> Exchange Server 2010 または最新 Service Pack の展開ドキュメント <br/> Exchange Server 2013年の計画し DeploymentExchange サーバー 2016年の計画と展開|
|証明書をインストールします。  <br/> |ダウンロードし、信頼されたルート証明機関 (CA) から Exchange UM サーバーごとに証明書をインストールします。 証明書は、相互トランスポート レベル セキュリティ (MTLS) ビジネス サーバーの Exchange UM と Skype を実行しているサーバー間での必要があります。  <br/> |管理者  <br/> |[Exchange Server ユニファイド メッセージングを実行するサーバーに証明書を構成します。](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|作成し、新しい Exchange が UM SIP ダイヤル プランを構成します。  <br/> |Exchange UM サーバーで、組織の特定の展開要件に基づいて SIP ダイヤル プランを作成します。  <br/> |Exchange 組織管理者  <br/> | [Microsoft Exchange Server 上のユニファイド メッセージングを構成します。](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|Exchange が UM SIP ダイヤル プランのセキュリティ設定を構成します。  <br/> |エンタープライズ VoIP トラフィックを暗号化するには、**セキュリティで保護された SIP**または**セキュリティで保護された**Exchange が UM SIP ダイヤル プランでセキュリティ設定を構成します。 これは、展開している場合に特に重要なステップまたは環境内のデバイスを Lync の電話のエディションを展開する計画です。 Exchange UM の統合を使用する環境で機能するデバイスを Lync の電話のエディション、Skype ビジネス サーバーの暗号化の設定をする必要があります、Exchange UM ダイヤル プランのセキュリティ設定に沿って配置します。 詳細については、「展開」のドキュメントを参照してください。  <br/> |Exchange 組織管理者  <br/> |Exchange 2010 または最新 Service Pack の場合は、次のドキュメントも参照してください。  <br/> 「[VoIP セキュリティ設定の構成](https://go.microsoft.com/fwlink/p/?LinkId=268697)」  <br/> Exchange 2013 では、「[ユニファイド メッセージング](https://go.microsoft.com/fwlink/p/?LinkId=266579)」を参照してください。  <br/> |
|ユニファイド メッセージング サーバーは、Exchange UM SIP ダイヤル プランに追加します。  <br/> |新しくインストールされたユニファイド メッセージング サーバーを、着信通話に応答および着信通話を処理できるようにするには、ユニファイド メッセージング サーバーを UM ダイヤル プランに追加しなければなりません。 この例では、Exchange が UM SIP ダイヤル プランにサーバーを追加します。  <br/> |管理者  <br/> Exchange Server 管理者  <br/> |Exchange 2010 または最新 Service Pack の場合は、「[UM サーバーのプロパティの表示または構成](https://go.microsoft.com/fwlink/p/?linkId=268682)」を参照してください。  <br/> Exchange 2013 では、「[ユニファイド メッセージング](https://go.microsoft.com/fwlink/p/?LinkId=266579)」を参照してください。  <br/> |
|SIP アドレスでメールボックスを構成します。  <br/> |Exchange UM 機能を使用するエンタープライズ VoIP ユーザーのメールボックスに SIP アドレスを割り当てます。  <br/> |Skype ビジネス サーバーの管理者の  <br/> Exchange 受信者の管理者  <br/> |Exchange 2010 または最新の service pack では、 [UM-Enabled ユーザーの SIP アドレスの変更](https://go.microsoft.com/fwlink/p/?LinkId=268699)を参照してください。  <br/> Exchange 2013 では、「[ユニファイド メッセージング](https://go.microsoft.com/fwlink/p/?LinkId=266579)」を参照してください。  <br/> |
|exchucutil.ps1 スクリプトを実行します。  <br/> |Exchange UM サービスを実行するサーバーで Exchange 管理シェルを開くし、は、次の exchucutil.ps1 のスクリプトを実行します。 <br/> <br/> • 助成金がビジネス サーバーの読み取りアクセス許可 Exchange UM Active Directory ドメイン サービス オブジェクトでは、具体的には、SIP の Skype のダイヤル プランの前のタスクで作成します。  <br/><br/> •、ユニファイド メッセージング IP ゲートウェイ オブジェクト Active Directory に作成ビジネス Server Enterprise Edition プールまたは Standard Edition サーバーの各 Skype のエンタープライズ VoIP が有効になっているユーザーをホストします。  <br/><br/> • は、Exchange UM ハント グループの各ゲートウェイを作成します。 ハント グループのパイロット ID は、対応するゲートウェイに関連付けられたダイヤル プランの名前になります。 複数のダイヤル プランが存在する場合は、これらは 1 対 1 でマップされる必要があります。  <br/> |Exchange 組織管理者  <br/> Exchange 受信者の管理者  <br/> |[Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1](#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|ビジネス サーバーのダイヤル プランには、Skype を構成します。  <br/> |Exchange 2010 と統合する場合は、Exchange UM ダイヤル プラン完全修飾ドメイン名 (FQDN) に一致する名前を持つ新しいエンタープライズ VoIP ダイヤル プランを作成します。  <br/> **注:** UM ダイヤル プランごとにこの操作を行う必要があります。 <br/> Exchange 2010 SP1 を統合する場合は、適切なグローバルまたはサイト レベルまたはプール レベルのエンタープライズ VoIP のダイヤル プランが構成されていることを確認します。  <br/> **注:** Exchange 2010 SP1 を統合する場合、Skype のダイヤル プランのビジネス サーバーと Exchange が UM SIP ダイヤル プランの名前を一致させる必要はありません。 <br/> |RTCUniversalServerAdmins  <br/> |[作成またはビジネス サーバーの Skype のダイヤル プランを変更します。](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|Exchange UM の統合ツールを実行します。  <br/> | ビジネス サーバーの Skype、 **ocsumutil.exe**を実行します。  <br/>  サブスクライバー アクセスおよび自動応答連絡先オブジェクトを作成します。 <br/>  Exchange UM ダイヤル プラン FQDN に一致する名前が、エンタープライズ VoIP のダイヤル プランがあることを検証します。 Exchange 2010 SP1 を実行している場合は後で、ダイヤル プラン名が一致する必要はありませんし、このツールの警告を無視できます。 <br/>  このツールは、Exchange UM の設定を Active Directory をスキャンされ、表示、作成、および連絡先オブジェクトを編集するビジネス サーバー管理者の Skype で動作します。 <br/> |RTCUniversalServerAdmins*と*RTCUniversalUserAdmins <br/> **重要な:** Ocsumutil.exe を正常に実行するには、ユーザーがこれらのグループの両方に属していなければなりません。 <br/> **注:** 連絡先オブジェクトを作成するには、新しい連絡先オブジェクトが保存されている Active Directory 組織単位 (OU) に正しいアクセス許可が ocsumutil.exe を実行するユーザーに必要です。 **許可 CsOUPermission**コマンドレットを実行して、このアクセス許可を与えることができます。 詳細については、Skype ビジネス サーバー管理シェルのドキュメントを参照してください。 <br/> |[ビジネス サーバーのボイス メール用 Skype の Exchange Server ユニファイド メッセージングを設定します。](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|必要に応じて、他のエンタープライズ VoIP の構成手順を実行します。  <br/> |サーバーまたはユーザーのエンタープライズ VoIP 設定を構成していない場合、次のいずれかの操作を行います。  <br/> • の展開および構成  <br/> および仲介サーバーを展開および構成します。  <br/> • 音声ポリシー、PSTN 使用法レコード、および発信通話ルートを定義します。  <br/> • エンタープライズ VoIP のユーザーを有効にします。  <br/> • は、必要に応じて、ダイヤル プランで特定のユーザーを構成します。  <br/> その他の構成手順を実行するを有効にするエンタープライズ VoIP 機能によって、必要があります。  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |次のセクションのトピックを参照してください。  <br/> •[音声ポリシーを構成する、PSTN 使用法レコード、およびビジネスのための Skype でのボイス ルート](../../deploy/deploy-enterprise-voice/voice-and-pstn.md) <br/> [Skype ビジネス サーバーでエンタープライズ VoIP を展開します。](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|Exchange UM のユーザーのエンタープライズ VoIP を有効にします。  <br/> |Exchange UM サーバーで、ユニファイド メッセージング メールボックス ポリシーが作成されている各ユーザーが独自の拡張機能番号の割り当てを持っていることを確認し、ユニファイド メッセージングのユーザーを有効にします。  <br/> |Exchange 受信者の管理者  <br/> |Exchange 2010 または最新 Service Pack の場合は、「[ユーザーのユニファイド メッセージングの有効化](https://go.microsoft.com/fwlink/p/?LinkId=268701)」を参照してください。  <br/> Exchange 2013 では、「[ユニファイド メッセージング](https://go.microsoft.com/fwlink/p/?LinkId=266579)」を参照してください。  <br/> |
   




## <a name="see-also"></a>関連項目

[Skype for Business での Exchange ユニファイド メッセージング統合の計画](unified-messaging.md)