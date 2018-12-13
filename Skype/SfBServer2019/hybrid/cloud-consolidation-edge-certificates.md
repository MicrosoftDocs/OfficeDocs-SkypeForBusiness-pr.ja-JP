---
title: エッジの証明書を更新します。
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: この付録には、チームおよびビジネス用の Skype のためのクラウドの統合の一部として、エッジの証明書を更新する詳細な手順が含まれています。
ms.openlocfilehash: bd7707add0962a827373f1d07de9f8f8f9d3ec7c
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247682"
---
# <a name="update-the-edge-certificate"></a>エッジの証明書を更新します。

SipDomain1 prem の環境が SipDomain2 でのクラウド環境への参加し、2 つの SIP ドメイン間で共有アドレス スペースの環境で適切なルーティングを確保できることを確認するのには重要なステップは、エッジの証明書を更新します。 この手順を実行する可能性がありますコンテキストの[チームおよびビジネス用の Skype のためのクラウドの統合](cloud-consolidation.md)の手順 14 を参照してください。 例では、SipDomain1 は AcquiredCompany です。<span>OriginalCompany は、com と SipDomain2。<span>com です。

純粋なオンライン テナント内に存在するすべての SIP ドメインを含むように、オンプレミス環境でのすべてのエッジ サーバーの証明書のサブジェクト代替名 (SAN) を更新する必要があります (任意の onmicrosoft を除外します<span>。com ドメインの場合)、フォームの"sip。\<ドメイン >"です。  この例では、これは、sip です。OriginalCompany。<span>com です。 この手順は、すべてのユーザーをクラウドに移行する前に重要です。

**手順に従います。**

1.  クラウド環境内のすべての SIP ドメインの SAN のすべての既存のエントリとその他のエントリには、エッジの新しい外部境界の証明書を取得 (を除く *. onmicrosoft.com ドメイン) フォームの"sip。<DomainName>」です。
2.  各エッジ サーバーで証明書をローカルにインストールし、各エッジ サービスの Skype のエッジ サービスを割り当てます。  詳細な手順は、[ビジネス サーバー 2015 の Skype でのエッジ サービスの展開](https://technet.microsoft.com/en-us/library/dn951368.aspx)で「外部エッジ インターフェイスの証明書」セクションを参照してください。
3.  各エッジ トランスポート サーバーのエッジ サービスを再起動します。 次の PowerShell コマンドを使用して 1 つのボックスで、これを行うことができます。

    ```
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>関連項目

[チームと Skype のビジネス向けのクラウド統合](cloud-consolidation.md)