---
title: 'Lync Server 2013: 統合ユニファイド メッセージングの機能'
TOCTitle: 統合ユニファイド メッセージングと Lync Server の機能
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48271194
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 統合ユニファイド メッセージングと Lync Server 2013 の機能

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 の エンタープライズ VoIP では、Exchange ユニファイド メッセージング (UM) インフラストラクチャを使用して、着信応答、着信通知、音声アクセス (ボイス メールを含む)、および自動応答サービスを提供します。

## 着信応答

着信応答は、ユーザーが電話に出られないときや通話が取り込み中のときに、ユーザーに代わって音声メッセージを受け取る機能です。個人用の応答メッセージの再生と、メッセージの録音ができます。メッセージはキューに登録され、ユーザーのメールボックスに配信されます。ユーザーのメールボックスは、Exchange メールボックス サーバーに格納されています。

発信者がメッセージを残すと、ユーザーの受信トレイにメッセージがルーティングされます。発信者がメッセージを残さなかった場合は、不在着信通知がユーザーのメールボックスに格納されます。 ユーザーが自分の受信トレイにアクセスするには、Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Outlook Web Access、Exchange ActiveSync テクノロジ、または Outlook Voice Access を使用します。 電子メールと同様の方法で、着信の件名と優先度を表示できます。

## Outlook Voice Access

Outlook Voice Access を使用すると、エンタープライズ VoIP ユーザーはボイス メールだけでなく、電子メール、予定表、およびテレフォニー インターフェイスの連絡先を含む Exchange 受信トレイにもアクセスできます。サブスクライバー アクセス番号は Exchange UM 管理者によって割り当てられます。

## 自動応答

自動応答は、外部のユーザーがダイヤルすると会社の代表部署につながるように電話番号を構成するための、Exchange UM の機能です。具体的には、外部からの発信者に音声でメニュー システムの操作を案内します。 利用できるオプションのリストは、Exchange UM 管理者が Exchange UM サーバー上で構成します。

## FAX サービス

Exchange UM には FAX 機能が含まれているので、ユーザーは Exchange のメールボックスで着信 FAX を受信できます。詳細については、Microsoft Exchange Server のドキュメントの「ユニファイド メッセージング」([http://go.microsoft.com/fwlink/?linkid=135652\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=135652%26clcid=0x411)) を参照してください。

> [!NOTE]
> Exchange UM サーバーによって提供される FAX サービスは、Microsoft Exchange Server 2010、最新のサービス パックが適用された Exchange 2010、または Exchange 2013 と統合されている Lync Server の展開では使用できません。

