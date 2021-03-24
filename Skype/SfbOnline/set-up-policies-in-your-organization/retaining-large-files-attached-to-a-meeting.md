---
title: Skype for Business 会議に添付された大きなファイルを保持する
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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Skype for Business 会議にファイルを添付すると、参加者はファイルを開いてダウンロードできます。 Skype for Business 会議に添付されたファイルは、メールボックスが訴訟ホールドに設定されている、Microsoft 365 または Office 365 アイテム保持ポリシーが適用されている、または Microsoft 365 コンプライアンス センターの電子情報開示ケースに関連付けられた保留にされている参加者のメールボックスに保持されます。 このコンテンツは、参加者のメールボックス内の回復可能なアイテム フォルダーに保存されます。
ms.openlocfilehash: 515f8b68db04a7acfc8eab2d7c639157cdb0da8d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100573"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Skype for Business 会議に添付された大きなファイルを保持する

Skype for Business 会議にファイルを添付すると、参加者はファイルを開いてダウンロードできます。 Skype for Business 会議に添付されたファイルは、メールボックスが訴訟ホールドに設定されている、Microsoft 365 または Office 365 アイテム保持ポリシーが適用されている、または Microsoft 365 コンプライアンス センターの電子情報開示ケースに関連付けられた保留にされている参加者のメールボックスに保持されます。 このコンテンツは、参加者のメールボックス **内の回復可能なアイテム** フォルダーに保存されます。
  
保留されているメールボックスに保持されているファイルはインデックスが作成されるため、参加者のメールボックスを検索するときにセキュリティ コンプライアンス センターでコンテンツ検索を実行するときに検索 &amp; できます。 ただし、30 MB を超える添付ファイルは、2 つ以上の小さいファイルに分割され、圧縮 (.zip) ファイルとして保存されます。 これらの  *小*  さいファイルのコンテンツは、検索用のインデックスが作成されていないので、コンテンツ検索で返されない場合があります。 ただし、 *これらのファイル*  のメタデータ (ファイル名や作成者など) は検索用にインデックスが作成され、コンテンツ検索で返される場合があります。
  
> [!IMPORTANT]
> Exchange Online メールボックスの MaxReceiveSize と MaxSendSize の設定は、Skype for Business 会議から大きなファイルを保持する機能に影響する可能性があります。 MaxReceiveSize と MaxSendSize の既定の設定は、それぞれ 36 MB と 35 MB です。 ただし、これらの既定の設定は小さすぎて、30 MB を超える Skype for Business 会議のファイルを保持する必要があります。 これは、Exchange Online でメッセージ添付ファイルや他のバイナリ データの Base64 エンコードが使用されるためです。 メッセージをエンコードすると、そのサイズは約 33% 増加します。 そのため、Skype for Business 会議の大きなファイルを確実に保持するには、保留にされたユーザーの MaxReceiveSize と MaxSendSize の両方の値を 39 MB に増やすることをお勧めします (前に説明した 30 MB のサイズ制限を約 33% 大きくします)。 そうしないと、Skype for Business 会議に添付された大きなファイルが保持されない可能性があります。 Exchange Online PowerShell で **Set-Mailbox -MaxReceiveSize** および **Set-Mailbox -MaxSendSize** コマンドを使用する方法の詳細については [、「Set-Mailbox」](/powershell/module/exchange/mailboxes/Set-Mailbox)を参照してください。
  
保留にされていないメールボックスには、会議データは保存されません。 たとえば、2 人の参加者のメールボックスに保持のマークが付いている 3 人の会議では、会議データは 2 人の参加者のメールボックスに保存されますが、メールボックスが保留されていない 3 人目の参加者のメールボックスには保存されません。
  
## <a name="related-topics"></a>関連項目
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[ポイント間ファイル転送をブロックする](block-point-to-point-file-transfers.md)

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

[組織で会議ポリシーを設定する](set-up-conferencing-policies-for-your-organization.md)
  
  
