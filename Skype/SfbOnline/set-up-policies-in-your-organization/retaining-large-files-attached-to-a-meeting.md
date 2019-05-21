---
title: Skype for Business 会議に添付されている大きなファイルを保持する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Skype for Business 会議にファイルを添付することができます。これにより、参加者はこの会議を開いてダウンロードすることができます。 Skype for Business 会議に添付されたファイルは、メールボックスが訴訟ホールドの対象になっているか、Office 365 アイテム保持ポリシーが適用されているか、Office 365 セキュリティの電子情報開示ケースに関連付けられている保留リストに含まれているすべての参加者のメールボックスに保持されます&amp;コンプライアンスセンター。 このコンテンツは、自分のメールボックスの参加者の [回復可能なアイテム] フォルダーに保存されます。
ms.openlocfilehash: 4a8022b522f933ff8897586f632764eda77c6a67
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297761"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Skype for Business 会議に添付されている大きなファイルを保持する

Skype for Business 会議にファイルを添付することができます。これにより、参加者はこの会議を開いてダウンロードすることができます。 Skype for Business 会議に添付されたファイルは、メールボックスが訴訟ホールドの対象になっているか、Office 365 アイテム保持ポリシーが適用されているか、Office 365 セキュリティの電子情報開示ケースに関連付けられている保留リストに含まれているすべての参加者のメールボックスに保持されます&amp;コンプライアンスセンター。 このコンテンツは、自分のメールボックスの参加者の [**回復可能なアイテム**] フォルダーに保存されます。
  
保留中のメールボックスに保存されているファイルはインデックス処理されるので、参加者のメール&amp;ボックスを検索するときに、セキュリティコンプライアンスセンターでコンテンツ検索を実行すると検索できます。 ただし、30 MB を超える添付ファイルは、2つ以上の小さいファイルに分割され、圧縮 (.zip) ファイルとして保存されます。 これらの小さいファイルの*内容*は検索用にインデックスされず、コンテンツ検索で返されないことがあります。 ただし、これらのファイルの*メタデータ*(ファイル名や作成者など) は検索用にインデックス処理されるため、コンテンツ検索で返される可能性があります。
  
> [!IMPORTANT]
> Exchange Online メールボックスの MaxReceiveSize と MaxSendSize の設定は、Skype for Business 会議から大きいファイルを保持する機能に影響する可能性があります。 MaxReceiveSize と MaxSendSize の既定の設定は、それぞれ 36 MB と 35 MB です。 ただし、これらの既定の設定は、30 MB を超える Skype for Business 会議のファイルを保持するには小さすぎます。 これは、Exchange Online でメッセージの添付ファイルとその他のバイナリデータの Base64 エンコードが使用されるためです。 メッセージがエンコードされると、サイズは約 33% 増加します。 そのため、Skype for Business 会議から大きいファイルが保持されるようにするには、MaxReceiveSize と MaxSendSize の値を 39 MB に増やすことをお勧めします (これについては、前に説明した 30 MB のサイズ制限より約 33% 大きくなります)。保留中のユーザーの場合。 そうしないと、Skype for Business 会議に添付されている大きなファイルが保持されないことがあります。 Exchange Online PowerShell での**MaxReceiveSize**と set-Mailbox **-maxsendsize**コマンドの使用について詳しくは、「[メールボックスを設定](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)する」をご覧ください。
  
保留になっていないメールボックスには、会議データが保存されません。 たとえば、2人の参加者のメールボックスが保持対象としてマークされている会議では、会議データは、その2人の出席者のメールボックスに保存されます。ただし、メールボックスは保留中ではありません。
  
## <a name="related-topics"></a>関連トピック
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[ポイントツーポイントファイル転送をブロックする](block-point-to-point-file-transfers.md)

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

[組織内の会議ポリシーをセットアップする](set-up-conferencing-policies-for-your-organization.md)
  
  
 