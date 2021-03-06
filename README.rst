fut14
=====


.. image:: https://travis-ci.org/oczkers/fut14.png?branch=master
        :target: https://travis-ci.org/oczkers/fut14

fut14 is a simple library for managing Fifa 14 Ultimate Team.
It is written entirely in Python.



Usage
-----

.. code-block:: pycon

    >>> import fut14
    >>> fut = fut14.Core('email', 'password', 'secret answer')

    >>> items = fut.searchAuctions('development',  # search items
    >>>     level='gold', category='fitness', min_price=300,  # optional parametrs
    >>>     max_price=600, min_buy=300, max_buy=400,  # optional parametrs
    >>>     start=0, page_size=60  # optional parametrs
    >>> )

    >>> for item in items:
    >>>     trade_id = item['tradeId']
    >>>     buy_now_price = item['buyNowPrice']
    >>>     trade_state = item['tradeState']
    >>>     bid_state = item['bidState']
    >>>     starting_bid = i['startingBid'],
    >>>     item_id = i['id'],
    >>>     timestamp = i['timestamp'],  # auction start
    >>>     rating = i['rating'],
    >>>     asset_id = i['assetId'],
    >>>     resource_id = i['resourceId'],
    >>>     item_state = i['itemState'],
    >>>     rareflag = i['rareflag'],
    >>>     offers = i['offers'],
    >>>     current_bid = i['currentBid'],
    >>>     expires = i['expires'],  # seconds left

    >>>     fut.bid(trade_id, 600)  # make a bid

    >>> items = fut.tradepile()  # get all items from trade pile

    >>> for item in items:
    >>>     fut.sell(item['item_id'], 150,  # put item on auction
                     buy_now=0, duration=3600)  # optional parametrs

    >>> fut.watchlist_delete(trade_id)  # removes item from watch list
    >>> fut.tradepile_delete(trade_id)  # removes item from tradepile

    to be continued ;-)
    ...


CLI examples
------------
.. code-block:: bash

    not yet
    ...


License
-------

GNU GPLv3
