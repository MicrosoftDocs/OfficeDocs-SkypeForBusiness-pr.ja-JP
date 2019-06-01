---
title: オンプレミス ユニファイド メッセージングと Skype for Business を統合するための展開プロセスの概要
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1bcadf0a-ca3d-436f-a2a0-09329d487b18
description: '概要: Skype for Business Server を Exchange 2013 または2016に統合する計画中に、このトピックを確認してください。'
ms.openlocfilehash: 3b83fdbc7c193056b689d92ddec6061cfc59ca25
ms.sourcegitcommit: 1336f6c182043016c42660d5f21632d82febb658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "34667506"
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>オンプレミス ユニファイド メッセージングと Skype for Business を統合するための展開プロセスの概要
 
**概要:** Skype for Business Server を Exchange 2013 または2016に統合する計画中に、このトピックを確認してください。
  
 Exchange ユニファイドメッセージング (UM) と Skype for Business Server を統合する場合は、このトピックで説明されているタスクを実行する必要があります。 また、「 [Skype For business での Exchange ユニファイドメッセージングの統合の計画](unified-messaging.md)」で説明されている計画と展開のベストプラクティスについて確認してください。 このトピックでは、Skype for Business Server を併置された仲介サーバーと共に展開し、Skype for Business Server のユーザーを有効にしていることを前提としていますが、エンタープライズ Voip を有効にするための展開と構成の手順はすべて実行していない可能性があります。「 [Skype For Business Server でのエンタープライズ voip の](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)展開」の説明を展開ドキュメントに記載しています。
 
> [!NOTE]
> 以前に認識されていた Exchange ユニファイドメッセージングは、Skype for Business Server 2019 では利用できなくなりました。電話システムを使用してボイスメールメッセージを記録し、ユーザーの Exchange メールボックスに記録したままにします。 詳細については、「[クラウドボイスメールサービスの計画](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)」を参照してください。
 
## <a name="unified-messaging-integration-process"></a>ユニファイド メッセージング統合プロセス

> [!IMPORTANT]
> 組織の Exchange 管理者と協力して、円滑かつ確実に統合されるようにするために、各タスクの実行を確認することが重要です。 
  
|**段階**|**手順**|**必要なグループおよび役割**|**「展開」のドキュメント**|
|:-----|:-----|:-----|:-----|
|次のいずれかを展開します。  <br/> •メールボックス  <br/> Microsoft Exchange Server 2010 または最新の service pack  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/>  |Microsoft Exchange Server 2013 を使用している場合は、次の Exchange Server の役割を同じフォレストまたは別のフォレストの Skype for Business サーバーとしてインストールします。  <br/> •クライアントアクセス  <br/> •メールボックス  <br/> Microsoft Exchange Server 2013 と Exchange ユニファイドメッセージング (UM) が異なるフォレストにインストールされている場合は、各 Exchange フォレストが Skype for Business Server フォレストを信頼するように構成します。  <br/> Exchange 2010 を使用している場合は、次の Exchange Server の役割を同じフォレストまたは別のフォレストの Skype for Business サーバーとしてインストールします。  <br/> •ユニファイドメッセージング  <br/> •ハブトランスポート  <br/> •クライアントアクセス  <br/> •メールボックス  <br/> Skype for Business Server と Exchange ユニファイドメッセージング (UM) が異なるフォレストにインストールされている場合は、各 Exchange フォレストが Skype for Business Server フォレストを信頼するように構成します。  <br/> |エンタープライズ管理者 (これが組織内で最初の Exchange Server である場合)  <br/> - または -  <br/> Exchange 組織管理者 (これが組織内で最初の Exchange Server ではない場合)  <br/> |お使いの Exchange Server のバージョンに適したドキュメントを参照してください。  <br/> Exchange Server 2010 または最新の service pack の展開に関するドキュメント <br/> Exchange Server 2013 計画と DeploymentExchange Server 2016 の計画と展開|
|証明書をインストールします。  <br/> |信頼されたルート証明機関 (CA) から各 Exchange UM サーバーの証明書をダウンロードしてインストールします。 証明書は、Exchange UM と Skype for Business Server が実行されているサーバー間の相互トランスポートレベルセキュリティ (MTLS) に必要です。  <br/> |管理者  <br/> |[Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-certificates-on-the-server-running-exchange-server-unified-messaging)|
|新しい Exchange UM SIP ダイヤルプランを作成して構成します。  <br/> |Exchange UM サーバーで、組織の特定の展開要件に基づいて SIP ダイヤルプランを作成します。  <br/> |Exchange 組織管理者  <br/> | [Microsoft Exchange Server でのユニファイドメッセージングの構成](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configuring-unified-messaging-on-microsoft-exchange-server) |
|Exchange UM SIP ダイヤルプランのセキュリティ設定を構成します。  <br/> |エンタープライズボイストラフィックを暗号化するには、Sip がセキュリティで**保護**されている、またはセキュリティで**保護**されている場合に、Exchange UM SIP ダイヤルプランのセキュリティ設定を構成します。 これは、お客様の環境に Lync Phone Edition のデバイスを展開または展開する予定がある場合に特に重要です。 Exchange UM との統合によって環境内で機能する Lync Phone Edition デバイスの場合、Skype for Business Server の暗号化設定は、Exchange UM ダイヤルプランのセキュリティ設定に合わせる必要があります。 詳細については、「展開」のドキュメントを参照してください。  <br/> |Exchange 組織管理者  <br/> |Exchange 2010 または最新 Service Pack の場合は、次のドキュメントも参照してください。  <br/> [UM ダイヤルプランで VoIP セキュリティを構成](https://go.microsoft.com/fwlink/p/?LinkId=268697)します。  <br/> Exchange 2013 については、「[ユニファイドメッセージング](https://go.microsoft.com/fwlink/p/?LinkId=266579)」を参照してください。  <br/> |
|ユニファイドメッセージングサーバーを Exchange UM SIP ダイヤルプランに追加します。  <br/> |新しくインストールされたユニファイド メッセージング サーバーを、着信通話に応答および着信通話を処理できるようにするには、ユニファイド メッセージング サーバーを UM ダイヤル プランに追加しなければなりません。 この場合は、Exchange UM SIP ダイヤルプランにサーバーを追加します。  <br/> |管理者  <br/> Exchange Server 管理者  <br/> |Exchange 2010 または最新の service pack については、「 [UM サーバーのプロパティを表示または構成](https://go.microsoft.com/fwlink/p/?linkId=268682)する」を参照してください。  <br/> Exchange 2013 については、「[ユニファイドメッセージング](https://go.microsoft.com/fwlink/p/?LinkId=266579)」を参照してください。  <br/> |
|SIP アドレスでメールボックスを構成します。  <br/> |Exchange UM 機能を使用するエンタープライズ Voip ユーザーのメールボックスに SIP アドレスを割り当てます。  <br/> |Skype for Business Server 管理者  <br/> Exchange 受信者の管理者  <br/> |Exchange 2010 または最新の service pack については、「 [UM が有効なユーザーの SIP アドレスを変更](https://go.microsoft.com/fwlink/p/?LinkId=268699)する」を参照してください。  <br/> Exchange 2013 については、「[ユニファイドメッセージング](https://go.microsoft.com/fwlink/p/?LinkId=266579)」を参照してください。  <br/> |
|exchucutil.ps1 スクリプトを実行します。  <br/> |Exchange UM サービスを実行しているサーバーで、Exchange 管理シェルを開き、次の操作を実行する exchucutil というスクリプトを実行します。 <br/> <br/> • Skype for Business Server へのアクセス許可を付与することで、Exchange UM Active Directory ドメインサービスオブジェクト、具体的には前のタスクで作成した SIP ダイヤルプランを読み取ります。  <br/><br/> •エンタープライズ Voip を有効にしているユーザーをホストしている Skype for Business Server Enterprise Edition プールまたは Standard Edition server ごとに、Active Directory 内にユニファイドメッセージング IP ゲートウェイオブジェクトを作成します。  <br/><br/> •各ゲートウェイの Exchange UM ハントグループを作成します。 ハント グループのパイロット ID は、対応するゲートウェイに関連付けられたダイヤル プランの名前になります。 複数のダイヤル プランが存在する場合は、これらは 1 対 1 でマップされる必要があります。  <br/> |Exchange 組織管理者  <br/> Exchange 受信者の管理者  <br/> |[Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md#configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1) |
|Skype for Business Server のダイヤルプランを構成します。  <br/> |Exchange 2010 と統合する場合は、新しいエンタープライズボイスダイヤルプランを作成し、Exchange UM ダイヤルプランの完全修飾ドメイン名 (FQDN) と一致する名前を付けます。  <br/> **注:** この操作は、各 UM ダイヤルプランについて行う必要があります。 <br/> Exchange 2010 SP1 と統合する場合は、適切なグローバル/サイトレベルまたはプールレベルのエンタープライズボイスダイヤルプランが構成されていることを確認します。  <br/> **注:** Exchange 2010 SP1 と統合する場合は、Skype for Business Server のダイヤルプランと Exchange UM SIP ダイヤルプランの名前を一致させる必要はありません。 <br/> |RTCUniversalServerAdmins  <br/> |[Skype for Business Server でダイヤルプランを作成または変更する](../../deploy/deploy-enterprise-voice/dial-plans.md) <br/> |
|Exchange UM 統合ツールを実行します。  <br/> | Skype for Business サーバーで、次のように**ocsumutil**を実行します。  <br/>  サブスクライバー アクセスおよび自動応答連絡先オブジェクトを作成します。 <br/>  Exchange UM ダイヤルプランの FQDN と一致する名前のエンタープライズボイスダイヤルプランがあることを検証します。 Exchange 2010 SP1 以降を実行している場合は、ダイヤルプラン名が一致している必要はありません。これに関するツールの警告は無視してかまいません。 <br/>  このツールは、Active Directory で Exchange UM 設定をスキャンし、Skype for Business Server 管理者が連絡先オブジェクトを表示、作成、編集できるようにすることによって機能します。 <br/> |RTCUniversalServerAdmins*と*RTCUniversalUserAdmins <br/> **重要:** Ocsumutil を正常に実行するには、ユーザーがこれらの両方のグループに属している必要があります。 <br/> **注:** 連絡先オブジェクトを作成するには、ocsumutil を実行しているユーザーは、新しい連絡先オブジェクトが保存されている Active Directory 組織単位 (OU) に適切なアクセス許可を持っている必要があります。 このアクセス許可は、**Grant-CsOUPermission** コマンドレットを実行することで付与されます。 詳細については、「Skype for Business Server 管理シェルのドキュメント」を参照してください。 <br/> |[Skype for Business Server ボイスメール用に Exchange Server ユニファイドメッセージングを構成する](../../deploy/integrate-with-exchange-server/exchangeunified-messaging-for-voice-mail.md) <br/> |
|必要に応じて、その他のエンタープライズボイス構成手順を実行します。  <br/> |サーバーまたはユーザーのエンタープライズ Voip 設定をまだ構成していない場合は、次の操作のいずれか、または複数の操作を行います。  <br/> •展開と構成  <br/> および仲介サーバーを展開および構成します。  <br/> •ボイスポリシー、PSTN 使用状況レコード、発信通話ルートを定義します。  <br/> •エンタープライズ Voip のユーザーを有効にします。  <br/> •ダイヤルプランを使用して特定のユーザーを構成する (オプション)。  <br/> 有効になっているエンタープライズ Voip 機能によっては、その他の構成手順が必要になることがあります。  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |次のセクションのトピックを参照してください。  <br/> • [Skype For business で音声ポリシー、PSTN 使用状況レコード、および音声ルートを構成する](../../deploy/deploy-enterprise-voice/voice-and-pstn.md) <br/> • [Skype For Business Server でエンタープライズ voip を展開する](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|エンタープライズボイスユーザーに Exchange UM を有効にします。  <br/> |Exchange UM サーバーで、ユニファイドメッセージングメールボックスポリシーが作成されていて、各ユーザーに固有の内線番号の割り当てが含まれていることを確認してから、そのユーザーのユニファイドメッセージングを有効にします。  <br/> |Exchange 受信者の管理者  <br/> |Exchange 2010 または最新の service pack については、「[ユーザーがユニファイドメッセージングを有効にする](https://go.microsoft.com/fwlink/p/?LinkId=268701)」を参照してください。  <br/> Exchange 2013 については、「[ユニファイドメッセージング](https://go.microsoft.com/fwlink/p/?LinkId=266579)」を参照してください。  <br/> |
   




## <a name="see-also"></a>関連項目

[Skype for Business での Exchange ユニファイド メッセージング統合の計画](unified-messaging.md)
