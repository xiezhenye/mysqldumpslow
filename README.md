# mysqldumpslow
improved version of official mysqldumpslow

#changes:
 * added -s ae, -s e to sort by rows exmained and average rows examined
 * added -z to combine different count of repeat times
 * fixed bug about repeat times substitude for string values

#usage:

    # /opt/mysql/bin/mysqldumpslow --help
    Usage: mysqldumpslow [ OPTS... ] [ LOGS... ]
    
    Parse and summarize the MySQL slow query log. Options are
    
      --verbose    verbose
      --debug      debug
      --help       write this text to standard output
    
      -v           verbose
      -d           debug
      -s ORDER     what to sort by (al, at, ar, ae, c, l, r, e, t), 'at' is default
                    al: average lock time
                    ar: average rows sent
                    at: average query time
                    ae: average rows examined
                     c: count
                     l: lock time
                     r: rows sent
                     e: rows examined
                     t: query time 
      -r           reverse the sort order (largest last instead of first)
      -t NUM       just show the top n queries
      -a           don't abstract all numbers to N and strings to 'S'
      -n NUM       abstract numbers with at least n digits within names
      -g PATTERN   grep: only consider stmts that include this string
      -h HOSTNAME  hostname of db server for *-slow.log filename (can be wildcard),
                   default is '*', i.e. match all
      -i NAME      name of server instance (if using mysql.server startup script)
      -l           don't subtract lock time from total time
      -z           don't show repeat times
    
