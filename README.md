# Snapshot Nolus


##### height: 1 269 033 | pruning: nothing: 100/0/10 | indexer: null
```
sudo systemctl stop nolusd
cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup 
nolusd tendermint unsafe-reset-all --home $HOME/.nolus --keep-addr-book 
curl http://135.181.183.93/nolus/nolus-rila_latest.tar | tar -xf - -C $HOME/.nolus
mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json 
sudo systemctl start nolusd
sudo journalctl -u nolusd -f --no-hostname -o cat
```
