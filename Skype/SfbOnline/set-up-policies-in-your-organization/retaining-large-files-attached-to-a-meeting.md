---
title: 会議に添付された大きなファイルSkype for Businessする
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
description: 会議にファイルを添付Skype for Business、参加者は開いてダウンロードできます。 Skype for Business 会議に添付されたファイルは、メールボックスが訴訟ホールドに設定されている、Microsoft 365 または Office 365 アイテム保持ポリシーが適用されている、または Microsoft 365 コンプライアンス センターの電子情報開示ケースに関連付けられている保留にされている参加者のメールボックスに保持されます。 このコンテンツは、参加者のメールボックス内の回復可能なアイテム フォルダーに保存されます。
ms.openlocfilehash: 74605b9aebf6d83619282d9cfc9094216d2fe6f1
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240109"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>会議に添付された大きなファイルSkype for Businessする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

会議にファイルを添付Skype for Business、参加者は開いてダウンロードできます。 Skype for Business 会議に添付されたファイルは、メールボックスが訴訟ホールドに設定されている、Microsoft 365 または Office 365 アイテム保持ポリシーが適用されている、または Microsoft 365 コンプライアンス センターの電子情報開示ケースに関連付けられている保留にされている参加者のメールボックスに保持されます。 このコンテンツは、参加者の **メールボックス内の回復可能なアイテム** フォルダーに保存されます。
  
保留のメールボックスに保持されているファイルはインデックスが作成されるため、参加者のメールボックスを検索するときにセキュリティ コンプライアンス センターでコンテンツ検索を実行するときに &amp; 検索できます。 ただし、30 MB を超える添付ファイルは、2 つ以上の小さなファイルに分割され、圧縮 (.zip) ファイルとして保存されます。 これらの  *小*  さいファイルのコンテンツは、検索用にインデックスが作成されないので、コンテンツ検索では返されない可能性があります。 ただし、 *これらのファイル*  のメタデータ (ファイル名や作成者など) は検索用にインデックスが作成され、コンテンツ検索で返される場合があります。
  
> [!IMPORTANT]
> Exchange Online メールボックスの MaxReceiveSize と MaxSendSize の設定は、会議から大きなファイルを保持する機能Skype for Businessがあります。 MaxReceiveSize と MaxSendSize の既定の設定はそれぞれ 36 MB と 35 MB です。 ただし、これらの既定の設定は小さすぎて、30 MB を超える会議Skype for Businessファイルを保持する必要があります。 これは、メッセージの添付Exchange Online他のバイナリ データの Base64 エンコードを使用する必要があるためです。 メッセージがエンコードされた場合、サイズは約 33% 増加します。 そのため、Skype for Business 会議の大きなファイルを確実に保持するには、保留にされているユーザーの MaxReceiveSize と MaxSendSize の両方の値を 39 MB (前に説明した 30 MB のサイズ制限より約 33% 大きい) に増やすることをお勧めします。 それ以外の場合、会議に添付された大きなSkype for Businessは保持されない可能性があります。 Exchange Online PowerShell で **Set-Mailbox -MaxReceiveSize** コマンドと **Set-Mailbox -MaxSendSize** コマンドを使用する方法の詳細については、Set-Mailbox に関するページ [を参照してください](/powershell/module/exchange/mailboxes/Set-Mailbox)。
  
保留ではないメールボックスには、会議データは保存されません。 たとえば、2 人の参加者のメールボックスが保持のためにマークされている 3 人の会議では、会議データは 2 人の参加者のメールボックスに保存されますが、メールボックスが保留されていない 3 人目の参加者のメールボックスには保存されません。
  
## <a name="related-topics"></a>関連項目
[カスタム外部アクセス ポリシーを作成する](create-custom-external-access-policies.md)

[ポイント対ポイントファイル転送をブロックする](block-point-to-point-file-transfers.md)

[組織のクライアント ポリシーをセットアップする](set-up-client-policies-for-your-organization.md)

[組織で会議ポリシーを設定する](set-up-conferencing-policies-for-your-organization.md)
  
  
