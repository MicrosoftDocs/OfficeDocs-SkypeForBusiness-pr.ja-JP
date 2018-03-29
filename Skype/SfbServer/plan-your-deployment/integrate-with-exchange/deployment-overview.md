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
description: '概要: は、Exchange 2013 でのビジネス サーバー 2015 の Skype を統合するために計画するときにこのトピックを参照します。'
ms.openlocfilehash: bf035712a635c8ed293ca65639d68c6cac8a5d9b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-overview-for-integrating-on-premises-unified-messaging-and-skype-for-business"></a>オンプレミス ユニファイド メッセージングと Skype for Business を統合するための展開プロセスの概要
 
**の概要:**Exchange 2013 でのビジネス サーバー 2015 の Skype を統合するために計画するときに、このトピックを確認します。
  
 ビジネス サーバー 2015 の Skype での Exchange ユニファイド メッセージング (UM) を統合する場合は、このトピックで説明されているタスクを実行する必要があります。 [ビジネス用の Skype での Exchange ユニファイド メッセージング統合の計画](unified-messaging.md)」に記載の計画と展開ベスト プラクティスを確認することを確認してあります。 ここでは配置されている仲介サーバーとのビジネス サーバー 2015 の Skype を展開し、ビジネス サーバー 2015 年の Skype のユーザーを有効にしているが、実行したことがないが企業を有効にするすべての展開と構成の手順ボイス、展開に関するドキュメントの[ビジネス サーバー 2015 の Skype でのエンタープライズ VoIP の展開](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)で説明します。
  
## <a name="unified-messaging-integration-process"></a>ユニファイド メッセージング統合プロセス

> [!IMPORTANT]
> 重要なことがスムーズに成功した統合を確実に実行が協力して、組織の Exchange 管理者は、タスクを確認するとするのです。 
  
|**フェーズ**|**手順**|**必須のグループとロール**|**展開に関するドキュメント**|
|:-----|:-----|:-----|:-----|
|次のいずれかを展開します。  <br/> • メールボックス  <br/> Microsoft Exchange Server 2010 または最新の service pack  <br/> • Microsoft Exchange Server 2013  <br/> • Microsoft Exchange Server 2016  <br/> |Microsoft Exchange Server 2013 を使用する場合、ビジネス サーバー 2015 の同じフォレストまたは別のフォレストのいずれかで Skype としての次の Exchange Server の役割をインストールします。  <br/> • クライアント アクセス  <br/> • メールボックス  <br/> 2013 の Microsoft Exchange Server および Exchange ユニファイド メッセージング (UM) が別のフォレスト内にインストールされている場合は、Skype のビジネス サーバー 2015 フォレストを信頼する場合は、各 Exchange フォレストを構成します。  <br/> Exchange 2010 を使用する場合、ビジネス サーバー 2015 の同じフォレストまたは別のフォレストのいずれかで Skype としての次の Exchange Server の役割をインストールします。  <br/> • はユニファイド メッセージング  <br/> • ハブ トランスポート  <br/> • クライアント アクセス  <br/> • メールボックス  <br/> Skype ビジネス サーバー 2015 および Exchange ユニファイド メッセージング (UM) は別々 のフォレストにインストールする場合は、Skype のビジネス サーバー 2015 フォレストを信頼する場合は、各 Exchange フォレストを構成します。  <br/> |エンタープライズ管理者 (これが組織内で最初の Exchange Server である場合)  <br/> - または -  <br/> Exchange 組織管理者 (これが組織内で最初の Exchange Server ではない場合)  <br/> |お使いの Exchange Server のバージョンに適したドキュメントを参照してください。  <br/> Exchange Server 2010 または最新のサービス パック展開 documentationExchange Server 2013 の計画と DeploymentExchange サーバー 2016 の計画と展開|
|証明書をインストールします。  <br/> |ダウンロードし、信頼されたルート証明機関 (CA) から Exchange UM サーバーごとに証明書をインストールします。 証明書は、相互トランスポート レベル セキュリティ (MTLS) ビジネス サーバー 2015 の Exchange UM と Skype を実行しているサーバー間での必要があります。  <br/> |管理者  <br/> ||
|作成し、新しい Exchange が UM SIP ダイヤル プランを構成します。  <br/> |Exchange UM サーバーで、組織の特定の展開要件に基づいて SIP ダイヤル プランを作成します。  <br/> |Exchange 組織管理者  <br/> |Exchange 2010 または最新の service pack は[、UM ダイヤル プランの作成](https://go.microsoft.com/fwlink/p/?linkId=268674)を参照してください。  <br/> Exchange 2013 では、「[ユニファイド メッセージング](https://go.microsoft.com/fwlink/p/?LinkId=266579)」を参照してください。  <br/> [Microsoft exchange ユニファイド メッセージングを構成します。](http://technet.microsoft.com/library/07547968-c59b-4dde-ace4-9fd286933759.aspx) <br/> |
|Exchange が UM SIP ダイヤル プランのセキュリティ設定を構成します。  <br/> |エンタープライズ VoIP トラフィックを暗号化するには、**セキュリティで保護された SIP**または**セキュリティで保護された**Exchange が UM SIP ダイヤル プランでセキュリティ設定を構成します。 これは、展開している場合に特に重要なステップまたは環境内のデバイスを Lync の電話のエディションを展開する計画です。 Exchange UM の統合を使用する環境で機能するデバイスを Lync の電話のエディション、Lync Server の暗号化の設定する必要があります、Exchange UM ダイヤル プランのセキュリティの設定に沿って配置します。 詳細については、「展開」のドキュメントを参照してください。  <br/> |Exchange 組織管理者  <br/> |Exchange 2010 または最新 Service Pack の場合は、次のドキュメントも参照してください。  <br/> [UM ダイヤル プランで VoIP セキュリティを構成](https://go.microsoft.com/fwlink/p/?LinkId=268697)します。  <br/> Exchange 2013 では、「[ユニファイド メッセージング](https://go.microsoft.com/fwlink/p/?LinkId=266579)」を参照してください。  <br/> |
|ユニファイド メッセージング サーバーは、Exchange UM SIP ダイヤル プランに追加します。  <br/> |新しくインストールされたユニファイド メッセージング サーバーを、着信通話に応答および着信通話を処理できるようにするには、ユニファイド メッセージング サーバーを UM ダイヤル プランに追加しなければなりません。 この例では、Exchange が UM SIP ダイヤル プランにサーバーを追加します。  <br/> |管理者  <br/> Exchange Server 管理者  <br/> |Exchange 2010 または最新の service pack では、[表示または構成する UM サーバーのプロパティ](https://go.microsoft.com/fwlink/p/?linkId=268682)を参照してください。  <br/> Exchange 2013 では、「[ユニファイド メッセージング](https://go.microsoft.com/fwlink/p/?LinkId=266579)」を参照してください。  <br/> |
|SIP アドレスでメールボックスを構成します。  <br/> |Exchange UM 機能を使用するエンタープライズ VoIP ユーザーのメールボックスに SIP アドレスを割り当てます。  <br/> |Skype ビジネス サーバー 2015 の管理者  <br/> Exchange 受信者の管理者  <br/> |Exchange 2010 または最新の service pack では、 [UM-Enabled ユーザーの SIP アドレスの変更](https://go.microsoft.com/fwlink/p/?LinkId=268699)を参照してください。  <br/> Exchange 2013 では、「[ユニファイド メッセージング](https://go.microsoft.com/fwlink/p/?LinkId=266579)」を参照してください。  <br/> |
|exchucutil.ps1 スクリプトを実行します。  <br/> |Exchange UM サービスを実行するサーバーで Exchange 管理シェルを開くし、は、次の exchucutil.ps1 のスクリプトを実行します。  <br/> • 助成金がビジネス サーバー 2015 を読み取るアクセス許可 Exchange UM Active Directory ドメイン サービス オブジェクトでは、具体的には、SIP の Skype のダイヤル プランの前のタスクで作成します。  <br/> •、ユニファイド メッセージング IP ゲートウェイ オブジェクト Active Directory に作成ビジネス サーバー 2015 エンタープライズ プールまたは Standard Edition サーバーの各 Skype のエンタープライズ VoIP が有効になっているユーザーをホストします。  <br/> • は、Exchange UM ハント グループの各ゲートウェイを作成します。 ハント グループのパイロット ID は、対応するゲートウェイに関連付けられたダイヤル プランの名前になります。 複数のダイヤル プランが存在する場合は、これらは 1 対 1 でマップされる必要があります。  <br/> |Exchange 組織管理者  <br/> Exchange 受信者の管理者  <br/> |[ExchUCUtil.ps1 を持つ Microsoft Exchange ユニファイド メッセージングを構成します。](http://technet.microsoft.com/library/07547968-c59b-4dde-ace4-9fd286933759.aspx) <br/> |
|Skype をビジネス サーバー 2015 のダイヤル プランを構成します。  <br/> |Exchange 2007 SP1 または service pack、または Exchange 2010 と統合する場合は、UM ダイヤル プラン完全修飾ドメイン名 (FQDN) に一致する名前を持つ新しいエンタープライズ VoIP ダイヤル プランを作成します。  <br/> **注:**UM ダイヤル プランごとにこの操作を行う必要があります。 <br/> Exchange 2010 SP1 を統合する場合は、適切なグローバルまたはサイト レベルまたはプール レベルのエンタープライズ VoIP のダイヤル プランが構成されていることを確認します。  <br/> **注:**Exchange 2010 SP1 では、Lync Server のダイヤル プランと統合すると、Exchange は UM SIP ダイヤル プランの名前が一致する必要はありません。 <br/> |RTCUniversalServerAdmins  <br/> |[ダイヤル プランと正規化の規則を構成します。](http://technet.microsoft.com/library/d4a4d803-f1a8-4ed9-907e-5f532a0f6c6b.aspx) <br/> |
|Exchange UM の統合ツールを実行します。  <br/> | ビジネス サーバー 2015 の Skype、 **ocsumutil.exe**を実行します。  <br/>  サブスクライバー アクセスおよび自動応答連絡先オブジェクトを作成します。 <br/>  Exchange UM ダイヤル プラン FQDN に一致する名前が、エンタープライズ VoIP のダイヤル プランがあることを検証します。 Exchange 2010 SP1 を実行している場合は後で、ダイヤル プラン名が一致する必要はありませんし、このツールの警告を無視できます。 <br/>  このツールは、Exchange UM の設定を Active Directory をスキャンされ、表示、作成、および連絡先オブジェクトを編集するのには管理者がビジネス サーバー 2015 Skype で動作します。 <br/> |RTCUniversalServerAdmins*と*RTCUniversalUserAdmins <br/> **重要な:**Ocsumutil.exe を正常に実行するには、ユーザーがこれらのグループの両方に属していなければなりません。 <br/> **注:**連絡先オブジェクトを作成するには、新しい連絡先オブジェクトが保存されている Active Directory 組織単位 (OU) に正しいアクセス許可が ocsumutil.exe を実行するユーザーに必要です。 **許可 CsOUPermission**コマンドレットを実行して、このアクセス許可を与えることができます。 詳細については、Skype ビジネス サーバー管理シェルのドキュメントを参照してください。 <br/> |[Microsoft Exchange Server 上のユニファイド メッセージングで作業する Lync Server を構成します。](http://technet.microsoft.com/library/1098ae4d-f57f-44f3-804e-39889d9fc14e.aspx) <br/> |
|必要に応じて、他のエンタープライズ VoIP の構成手順を実行します。  <br/> |サーバーまたはユーザーのエンタープライズ VoIP 設定を構成していない場合、次のいずれかの操作を行います。  <br/> • の展開および構成  <br/> および仲介サーバーを展開および構成します。  <br/> • 音声ポリシー、PSTN 使用法レコード、および発信通話ルートを定義します。  <br/> • エンタープライズ VoIP のユーザーを有効にします。  <br/> • は、必要に応じて、ダイヤル プランで特定のユーザーを構成します。  <br/> その他の構成手順を実行するを有効にするエンタープライズ VoIP 機能によって、必要があります。  <br/> |RTCUniversalServerAdmins  <br/> RTCUniversalUserAdmins  <br/> |次のセクションのトピックを参照してください。  <br/> •[音声ポリシーを構成する、PSTN 使用法レコード、およびビジネス 2015年の Skype でのボイス ルート](../../deploy/deploy-enterprise-voice/voice-and-pstn.md) <br/> [ビジネス サーバー 2015 の Skype でエンタープライズ VoIP を展開します。](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) <br/> |
|Exchange UM のユーザーのエンタープライズ VoIP を有効にします。  <br/> |Exchange UM サーバーで、ユニファイド メッセージング メールボックス ポリシーが作成されている各ユーザーが独自の拡張機能番号の割り当てを持っていることを確認し、ユニファイド メッセージングのユーザーを有効にします。  <br/> |Exchange 受信者の管理者  <br/> |Exchange 2010 または最新の service pack では、[ユーザーのユニファイド メッセージングを有効にする](https://go.microsoft.com/fwlink/p/?LinkId=268701)を参照してください。  <br/> Exchange 2013 では、「[ユニファイド メッセージング](https://go.microsoft.com/fwlink/p/?LinkId=266579)」を参照してください。  <br/> |
   
## <a name="see-also"></a>関連項目

#### 

[ビジネス用の Skype での Exchange ユニファイド メッセージング統合の計画](unified-messaging.md)

