This does not happen if you explicitly open the stdin connection.

#!/usr/bin/env Rscript
f <- file("stdin")
open(f)
while(length(line <- readLines(f,n=1)) > 0) {
  write(line, stderr())
  # process line
}
